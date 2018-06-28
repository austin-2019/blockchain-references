#### https://www.codeproject.com/Articles/1115639/Build-your-own-Bitcoin-wallet
#### Build your own Bitcoin wallet
##### Ádám Ficsór, 20 Feb 2017

#### EXCERPTS AND QUOTES FROM THE PAGE AS OF June 28, 2018

##### Clone the project from GitHub: DotNetWallet.

#####  Background
##### In order to be able to follow on this article you need to know C# and need to be familiar with NBitcoin. Preferably you have already been digging into the Bitcoin C# book before.

#####  Design choices
1. We want a cross-platform wallet and .NET Core is our platform of choice.  
1. NBitcoin is the most populat C# Bitcoin library today, therefore we are going to use it.
1. We don't need a GUI just yet, therefore it will be a CLI wallet.

#####  There are roughly three way to communicate with the Bitcoin network: as a full node, as an SPV node or through an HTTP API.  This tutorial will use QBitNinja's HTTP API, from Nicolas Dorier, the creator of NBitcoin, but I am planning to expand it with a full-node communication.

#####  At this point (2016.11.29) it is unclear if Segregated Witness will activate on the Bitcoin network, therefore I am not incorporating it in this tutorial for now.

#####  I kept the concepts simple, so you can understand them. This of course comes with inefficiencies. After this tutorial you can take a look at HiddenWallet, the successor of this wallet. So you get a production ready version, with bug and efficiency fixes.

