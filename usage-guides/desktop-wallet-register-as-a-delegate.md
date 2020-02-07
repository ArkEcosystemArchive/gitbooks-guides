# How To Register And Become A Delegate

## ARK: How To Register And Become A Delegate

_**Being an ARK delegate is a serious responsibility, and with great responsibility comes great rewards. Not only in forging rewards, but also the reward of the invaluable knowledge you acquire as you make connections and help secure the ARK blockchain network.**_

This guide will help you get started with registering a delegate and posting your delegate proposal.

> **Make your proposal at the community run website\*:** [**https://arkdelegates.io/**](https://arkdelegates.io/)

_\* ARK Delegates is a community ran project and we are not responsible for its content._

_“The price of greatness is responsibility!” — Winston Churchill_

## How To Register Your Own Delegate? <a id="3b08"></a>

The first step in your journey to becoming an ARK Delegate is to register your unique delegate name on the blockchain. This name serves as your identifier so others will be able to vote for you.

### 1. Download latest Desktop Wallet <a id="1a5a"></a>

[**Download**](https://wallet.ark.io/) latest ARK Desktop Wallet for your OS.

### 2. Prepare your wallet address <a id="dd70"></a>

Next, you will use one of your ARK addresses \(or create a new one\) that will become your delegate address. For this guide, we will create a new address and illustrate all of the steps involved. Our delegate will be created on the Development Network or _Devnet_ \(_you can reproduce same steps on other networks such as the Public Network — Mainnet or other private / public Bridgechains_\).

_Tip: we_ _**strongly**_ _suggest you try this first on the Devnet. This will allow you to become familiar with the workings of ARK as you setup your first node and navigate the entire process._

Once in Desktop Wallet, click on _**‘Create Wallet’.**_

![](../.gitbook/assets/howtobecomeadelegateimage1.png)

You will be presented with pre-generated ARK \(DARK in Devnet\) addresses. Chose the one you like. It will then show a green checkmark. You can also click on the refresh button to generate new addresses. Once you make a selection, click ‘_**Next**_’ to continue.

![](../.gitbook/assets/howtobecomeadelegateimage2.png)

You will be presented with the passphrase corresponding to your selected address. The passphrase consists of 12 words in a specific order — make sure you create a backup! We strongly suggest writing it on a piece of paper and saving it on an encrypted drive. If you lose this passphrase you lose access the ARK address for this account \(and in this case, to the delegate\). You can use the copy icon to copy it and save it to your preferred medium.

![](../.gitbook/assets/howtobecomeadelegateimage3.png)

The verification step is where you will confirm you have backed up your 12 word passphrase. If you click ‘_Verify each passphrase word’_ you will need to enter the entire 12 word phrase in the correct order. Otherwise you can verify by entering 3rd, 6th and 9th word of the passphrase.

![](../.gitbook/assets/howtobecomeadelegateimage4.png)

The next step gives you the option to encrypt your passphrase, meaning you can save your 12 word passphrase locally by encrypting it with a custom password. So, instead of entering the entire passphrase to sign a transaction, you can instead sign transactions with your password. If you set a password and then forget it, you can still access your account by re-importing it with the 12 word passphrase. We will skip this step and not enter a password.

![](../.gitbook/assets/howtobecomeadelegateimage5.jpeg)

The last step is to confirm the settings of your wallet. Since we’ll be registering it for a delegate we won’t name it.

![](../.gitbook/assets/howtobecomeadelegateimage6.jpeg)

After clicking ‘**Done**’ you will need to add DARK \(or ARK\) coins to your new empty wallet. Send coins to the public address seen in the upper left corner of the wallet. You can copy the address by clicking on the copy icon.

![](../.gitbook/assets/howtobecomeadelegateimage7.jpeg)

> You can request DARK \(Development coin\) in our [**public Slack**](https://ark.io/slack) \(channel \#devnet\) or on DARK faucet site ran by one of our delegates at [**https://devnet.money/**](https://devnet.money/).

### 3. Register your delegate name <a id="a7d5"></a>

Once you have coins in your wallet you can register your delegate. This is done by clicking the 3 vertical dots in the upper right corner. Additional options appear including the ‘_**Register delegate**_’ button.

![](../.gitbook/assets/howtobecomeadelegateimage8.jpeg)

Now you can input your unique delegate name. You must use lower case letters, and the name can also contain numbers and some special keys \[!@$&\_.\]. The name must not have already been used, cannot contain spaces, and can be up to 20 characters in length. We suggest you use something memorable and short so others will be able to find you. We will register a delegate with a name ‘taco’, select the average fee, and input our passphrase. If you encrypted your passphrase at the wallet creation page you will need to input your password instead. Click ‘**Next**’ once you are done.

![](../.gitbook/assets/howtobecomeadelegateimage9.jpeg)

The final step is to review and sign your transaction by pressing the ‘**Send**’ button. This will broadcast your transaction to the network.

![](../.gitbook/assets/howtobecomeadelegateimage10.jpeg)

That’s it! Now you only need to wait for the tx to be confirmed and included in a block. Wait a few seconds, and click on the refresh button in the upper menu. You will soon see your Delegate registration tx in the list below.

![](../.gitbook/assets/howtobecomeadelegateimage11.jpeg)

After next wallet restart, you will also see your delegate name in the upper corner of the wallet:

![](../.gitbook/assets/howtobecomeadelegateimage12.jpeg)

We are now ready to go on to the next step — setting up your server.

### 4. Setting up new ARK Core server <a id="3ee7"></a>

As a final step, you will need to prepare and configure your server for it to be ready to process blocks and transactions, if you are voted into the active delegation. For that, we have prepared a detailed guide for you to follow here:

> _If you run into any kind of troubles don’t hesitate to join our_ [_**ARK Slack**_](https://ark.io/slack)_, either go to \#delegate, \#devnet, or \#help channel._

### 5. Registering 2nd passphrase \(optional\) <a id="f43e"></a>

If you will be running a delegate, we strongly recommend registering a 2nd passphrase for your wallet. This optional step can prevent catastrophe if an unauthorized person gains access to your server where your delegate is running \(and if you set a plain passphrase on the server\). If a hacker gets access to your 1st passphrase they won’t be able to steal funds if you have registered a 2nd passphrase, since both are needed to sign transactions.

{% hint style="danger" %}
Make a backup of your 1st and 2nd passphrase. If you lose either, you will lose access to your account and will no longer be able to send and sign transactions.
{% endhint %}

Once in your wallet, click on the 3 vertical dots icon in the upper right corner to open additional options, and after that, click on the ‘**2nd passphrase**’ button.

![](../.gitbook/assets/howtobecomeadelegateimage13.jpeg)

You will be presented with a 2nd signature passphrase \(again consisting of 12 words\). **Write them down properly and copy to a secure medium.** You also have a refresh button if you wish to change them, and copy to clipboard if you want to paste your passphrase somewhere for storing. Click ‘**Next**’ once you have it backed up.

![](../.gitbook/assets/howtobecomeadelegateimage14.jpeg)

You will now need to confirm your 2nd passphrase and sign its transaction. Write or click on the 3rd, 6th and 9th word from your previously saved 2nd signature passphrase to confirm, select a tx fee and write or paste in your 1st passphrase. After you are done with the steps click on ‘**Next**’.

![](../.gitbook/assets/howtobecomeadelegateimage15.jpeg)

The last step is to confirm and broadcast your 2nd signature transaction. Click on ‘**Send**’.

![](../.gitbook/assets/howtobecomeadelegateimage16.jpeg)

All done! You have now successfully registered a 2nd passphrase for additional security. You can refresh your account by clicking on the refresh icon and see your tx in the list!

![](../.gitbook/assets/howtobecomeadelegateimage17.jpeg)

