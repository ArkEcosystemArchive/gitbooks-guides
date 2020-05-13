# ARK Messenger Tutorial — Part Three

**Welcome everyone to the final part in our series of tutorials based on the ARK Messenger Proof-of-Concept \(PoC\). During** [**Part One**](https://blog.ark.io/ark-messenger-tutorial-part-one-30068eb8619e)**, we set up a development environment and deployed our own custom bridgechain. During** [**Part Two**](https://blog.ark.io/ark-messenger-tutorial-part-two-e49e1fbd0b27)**, we created a custom transaction and tested it. This series was created in-part with documentation provided by Delegate** [**Lemii**](https://github.com/Lemii) **as part of his** [**ARK Messenger**](https://arkmessenger.io/) **Proof-of-Concept which was funded by the** [**ARK Grants Program**](https://ark.io/grants)**.**

Now that we have reached the conclusion of this series, it is time to finally launch the Proof-of-Concept. After launching the PoC we will highlight the unique ways in which building on ARK made the ARK Messenger PoC possible.

## Launching the PoC <a id="e21c"></a>

The bridgechain that supports the ARK Messenger was launched using the [ARK Deployer](https://ark.io/deployer). From a development standpoint, ARK Deployer is one of the easiest ways to launch a blockchain for your project. However, to build the ARK Messenger PoC, some configurations were made so that each consequent cloning of [the repository](https://github.com/ArkEcosystem/poc-ark-messenger-core) would include the aforementioned changes. The changes outlined below show just how easy it is to build and modify your blockchain on ARK.

### Including the custom transaction <a id="e072"></a>

* The files pertaining to the custom transaction we created were placed in the [/plugins/](https://github.com/ArkEcosystem/poc-ark-messenger-core/tree/master/plugins/message-transaction) folder.
* The custom transaction was added as a plugin to the bridgechain by inserting `"message-transaction": {}`, at the end of the [plugins.js](https://github.com/ArkEcosystem/poc-ark-messenger-core/blob/master/packages/core/bin/config/testnet/plugins.js) file.

### Disabling API caching <a id="b691"></a>

By default, the API caches results that are returned to the user. While this is usually a very nice feature to have, for a chat application where responsiveness is important, it is not the behavior that we want. Therefore, API caching was disabled in the [plugins.js](https://github.com/ArkEcosystem/poc-ark-messenger-core/blob/master/packages/core/bin/config/testnet/plugins.js) file:

```typescript
"@arkecosystem/core-api": {
    cache: { enabled: false },
    …    
},
```

### Disabling count estimates <a id="361d"></a>

By default, the API returns estimates of the total count. For ARK Messenger, we prefer to use accurate numbers, and therefore force this setting in an [environment variable](https://github.com/ArkEcosystem/poc-ark-messenger-core/blob/master/packages/core/bin/config/testnet/.env) that is used in the configuration:

```typescript
CORE_API_NO_ESTIMATED_TOTAL_COUNT=true
```

### Setting a minimum network reach <a id="3470"></a>

Since ARK Messenger is launched as a PoC, it is being run on a Testnet. In this network, no other nodes are connected to the network. To make sure that the forger process does not refuse to forge blocks due to not adhering to the minimum network reach, we configure it to be 0 in the [plugins.js](https://github.com/ArkEcosystem/poc-ark-messenger-core/blob/master/packages/core/bin/config/testnet/plugins.js) file:

```typescript
"@arkecosystem/core-p2p": {
    server: {
        …
        minimumNetworkReach: 0,
    },
},
```

Once the above changes have been made, you are ready to launch the Proof-of-Concept! The ARK Messenger is meant to be a community initiative where everyone can get involved. If you would like to contribute, feel free to submit your issues/pull requests to the [Messenger Client](https://github.com/Lemii/poc-ark-messenger) and [Core](https://github.com/ArkEcosystem/poc-ark-messenger-core) repositories.

## Building with ARK <a id="1b26"></a>

As the ARK team continues to make improvements to our wide suite of products, we want to continue to make the ARK platform one of the best and most reliable places to build your blockchain solutions.

Throughout this series, we have seen several ways that building on ARK adapted to the needs of this particular PoC. As we wrap up our series, let us highlight a few of them now.

### **Custom Transactions** <a id="9ca6"></a>

In order to create the transactions that would become the basis of ARK Messenger, modifications needed to be made to some of the existing transaction types within ARK Core. For this purpose, ARK has made it easy to make these changes through our [Generic Transaction Interface](https://blog.ark.io/ark-core-gti-introduction-to-generic-transaction-interface-57633346c249) \(GTI\). The purpose of GTI is to give developers an easy way to implement and include new transaction types in the ARK Core without having to modify large parts of the ARK Core.

If you would like to learn more about developing Custom Transaction Types with GTI, then read [here](https://blog.ark.io/an-introduction-to-blockchain-application-development-part-2-2-909b4984bae).

### **ARK Deployer** <a id="ec61"></a>

By using the ARK Deployer, the ARK Messenger’s stand-along blockchain was created in a quick and efficient manner. The blockchain created was also adapted to meet the needs of this specific PoC. The ARK Deployer allows anyone to be able to prepare, customize and deploy their blockchain in just a few simple steps.

If you would like to take a closer look at how this is all possible, please feel free to read the documentation regarding the ARK Deployer [here](https://deployer.ark.dev/).

## Funded by ARK Grants <a id="16eb"></a>

In case you haven’t heard, the ARK Messenger PoC was fully funded by the [ARK Grants](https://blog.ark.io/introducing-ark-grants-a-development-incentive-program-backed-by-1-million-ark-b0b26ec65390) program. ARK Grants is a developer incentive program aimed at our growing community of developers. Developers can receive funding for building ARK-based PoC’s, plugins and full production-ready applications. The program is being backed by 1 million ARK and currently accepting applications!

> **Learn about the ARK Grants guidelines and application process at** [**http://ark.io/grants**](http://ark.io/grants)

Thank you for joining us in this series! If you have any questions make sure to consult our documents on the [Learn ARK](https://learn.ark.dev/core-getting-started/setting-up-your-development-environment) hub. In addition, our team and community developers are active on [Slack](https://ark.io/slack) so do not hesitate to reach out!

## ARK Messenger Tutorial Series <a id="fb75"></a>

If you have missed other ARK Messenger Tutorials, you can read them by following the links below:

* [**Part One**](https://blog.ark.io/ark-messenger-tutorial-part-one-30068eb8619e)
* [**Part Two**](https://blog.ark.io/ark-messenger-tutorial-part-two-e49e1fbd0b27)
* **Part Three**

