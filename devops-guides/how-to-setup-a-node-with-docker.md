---
description: A Production and Development Guide For Setting Up Docker Images With Core.
---

# How To Setup A Node With Docker

## Introduction

Docker is the de facto industry standard for packaging applications into a container. By doing so, all dependencies, such as the language runtimes, operating system, and libraries are combined with the product.

### Prerequisites

Prerequisites to be installed:

* [Docker Engine](https://docs.docker.com/install)
* [Docker Compose](https://docs.docker.com/compose/install)

### Supported Cloud Providers

Different cloud providers offer specific products to host your Docker containers, such as:

* [Google App Engine](https://cloud.google.com/appengine/)
* [AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)
* [Azure](https://azure.microsoft.com/en-us/services/kubernetes-service/docker/)
* [Digital Ocean](https://www.digitalocean.com/products/one-click-apps/docker/)

Orchestrators with Docker as a first class citizen:

* [Kubernetes](https://kubernetes.io/)
* [Nomad](https://www.nomadproject.io/)
* [Mesos](http://mesos.apache.org/)

## Production Setup

{% hint style="success" %}
ARK Core Production ready Docker images are now available at [Docker Hub](https://hub.docker.com/r/arkecosystem/core)
{% endhint %}

### Get The Needed Docker Files

The code sample below downloads the needed files from our official [GitHub Core repository](https://github.com/ArkEcosystem/core/tree/master/docker/production).  

{% hint style="info" %}
`Set NETWORK=mainnet`if you prefer to run a Mainnet node. ``
{% endhint %}

```bash
NETWORK=devnet
mkdir ~/$NETWORK 
cd ~/$NETWORK
curl -sOJ https://raw.githubusercontent.com/ARKEcosystem/core/master/docker/production/$NETWORK/docker-compose.yml 
curl -sOJ https://raw.githubusercontent.com/ARKEcosystem/core/master/docker/production/$NETWORK/$NETWORK.env
```

### Running a Relay Node

```
cd ~/$NETWORK     # (NETWORK = devnet || mainnet)
docker-compose up -d
```

This will run two separate containers. One for Core itself and another one for PostgreSQL.

### How To Run a Relay and a Forger Node

#### Prerequisites to be installed:

* [OpenSSL](https://www.openssl.org/)

Two additional steps are needed to be able to run a forger:

**Step 1**: `MODE` has to be set to `forger` `(MODE=forger)` in your `$NETWORK.env` file.

```text
cd ~/$NETWORK
sed -i 's/^MODE=relay/MODE=forger/g $NETWORK.env
```

**Step 2.** Configure your delegate secret and password. _Just use the additional script **enc.sh**._

You will be asked to enter your delegate secret, followed by entering your password twice. Script will create a new folder named `enc`, containing set of encrypted public and private keys.

{% hint style="danger" %}
Folder **enc** is needed during core container startup. After making sure your **forger** is up and running it is preferably to delete it. The disadvantage of this would be that if you your server gets rebooted or simply core container restarted, you will have repeat step 2. 
{% endhint %}

#### Now let's run the forger:

This will fire up two separate containers. One for Core itself and another one for PostgreSQL.

#### Custom Settings

{% hint style="info" %}
If you prefer to use custom DB Name, DB User and DB Password simply adjust variables **POSTGRES\_PASSWORD, POSTGRES\_USER, POSTGRES\_DB** \(file=docker-compose.yml\) and **CORE\_DB\_PASSWORD, CORE\_DB\_USERNAME** and **CORE\_DB\_DATABASE** \(**file=$NETWORK.env**\) correspondingly. For a full list of Core variables go [here](core-environment-variables.md).

You can also change default log levels by adjusting variables **CORE\_LOG\_LEVEL** and **CORE\_LOG\_LEVEL\_FILE** \(**file=$NETWORK.env**\). Note that _DEBUG_ level will probably add some CPU overhead during network sync.
{% endhint %}

**In case you want to use a remote PostgreSQL server simply adjust variable `CORE_DB_HOST` in your `$NETWORK.env` and run only Core container:**

```text
cd ~/$NETWORK
docker-compose up -d core
```

## FAQ

### **How Do I Start With Empty DB?**

Just execute the following code:

```text
cd ~/$NETWORK
docker-compose down -v
docker-compose up -d
```

### **Where Are the Config Files and Logs Located?**

ARK Core container mounts by default the following local paths as volumes:

```text
~/.config/ark-core
~/.local/share/ark-core
~/.local/state/ark-core
```

Having that said, your config files are locally accessible under:

```text
~/.config/ark-core/$NETWORK/
```

Pool database as well as db snapshots are locally accessible under:

```text
~/.local/share/ark-core/$NETWORK/
```

Log files are locally accessible under:

```text
~/.local/state/ark-core/$NETWORK/
```

Alternative way of following the logs would be, by using the command:

```text
docker logs --tail 50 core-$NETWORK -f
```

### **How Do I Start Everything from Scratch?**

Just use the **`purge_all.sh`** script.

### How To Build Your Own ARK Core Docker Image

This requires cloning [ARK Core Github repository](https://github.com/ArkEcosystem/core).

```text
cd ~/
git clone https://github.com/ArkEcosystem/core
```

Custom Docker image builds of ARK Core are possible by using the file `docker-compose-build.yml`. Make your own modifications of ARK Core source code and run your custom container by executing:

```text
cd ~/core/docker/production/$NETWORK     # (NETWORK = devnet || mainnet)
docker-compose -f docker-compose-build.yml up -d
```

This will build your ARK Core Docker image and run two separate containers. One for Core itself and another one for PostgreSQL.

### How To Update Core Version Within Docker Image

#### Option 1: Docker Live Updates Are Now Possible With [CLI](https://docs.ark.io/guidebook/core/cli.html)

As a preliminary step, installation of development tools is necessary \(only needed once, when doing initial update\):

```text
docker exec -it core-$NETWORK sudo apk add make gcc g++ git python
```

> We are all set! Run the update and follow instructions:

```text
docker exec -it core-$NETWORK ark update
```

{% hint style="info" %}
Updates and all changes made to the containers are kept even on container or host restart.
{% endhint %}

#### Option 2: Update is also possible by destroying and running Core container from scratch, so it downloads the latest image.

{% hint style="danger" %}
Make sure you destroy only Core container in order to keep your database and avoid syncing the blockchain from zero block. The commands example below does this: 
{% endhint %}

```text
cd ~/$NETWORK 
docker stop core-$NETWORK
docker rm core-$NETWORK
docker rmi $(docker images -q)
docker-compose up -d core
```

## Development

### Generate the Configurations

ARK Core include several `Dockerfile` and `docker-compose.yml` templates to ease development. They can be used to generate different configurations, depending on the network and token.

For instance, you could use this command:

This command creates a new directory \(`docker`\) that contains 1 folder per network.

### Containerize the Persistent Store

#### **Run a PostgreSQL container while using NodeJS from your local environment.**

This configuration is well suited when you are not developing ARK Core, but instead working with the API. By tearing down the PostgreSQL container, you reset the Nodes blockchain.

{% hint style="info" %}
PostgreSQL is run in a separate container and it's port gets mapped to your `localhost`, so you should not have PostgreSQL running locally.
{% endhint %}

Clone [ARK Core Github repository](https://github.com/ArkEcosystem/core):

```text
cd ~/
git clone https://github.com/ArkEcosystem/core
```

```text
cd ~/core/docker/development/$NETWORK     # (NETWORK = testnet || devnet)
docker-compose up
```

To run the containers in the [background](https://docs.docker.com/engine/reference/run/):

_In case you need to start with a clean Database:_

```text
docker-compose down -v
docker-compose up -d
```

## Serve ARK Core as a Collection of Containers

#### **Run a PostgreSQL container, build and run ARK-Core using a mounted volume.**

When a container is built, all files are copied inside the container. It cannot interact with the host's filesystem unless a directory is specifically [mounted](https://docs.docker.com/storage/volumes/) during container start. This configuration works well when developing ARK Core itself, as you do not need to rebuild the container to test your changes.

{% hint style="success" %}
Along with PostgreSQL container, now you also have a NodeJS container which mounts your local ark-core git folder inside the container and installs all NPM prerequisites.
{% endhint %}

```text
cd ~/core/docker/development/$NETWORK      # (NETWORK = testnet || devnet)
docker-compose up -d
```

_You can now enter your ark-core container and use NodeJS in a Docker container \(Linux environment\)._

```text
docker exec -it ark-$NETWORK-core bash
```

_Need to start everything from scratch and make sure there are no remaining cached containers, images or volumes left? Just use the **purge\_all.sh** script._

{% hint style="danger" %}
**Development files/presets are not Production ready**. Official Production ARK-Core Docker images are now available at [Docker Hub](https://hub.docker.com/r/arkecosystem/core).
{% endhint %}

