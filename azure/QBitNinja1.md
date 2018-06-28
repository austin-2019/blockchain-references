#### https://qbitninja.docs.apiary.io/#

#### QUOTES FROM THE PAGE, as of June 28, 2018

#### QBit Ninja INTRODUCTIONQBit Ninja is an open source web service API to query the blockchain and for tracking wallets.
##### There are two public servers:
1. api.qbit.ninja for MainNett
1. api.qbit.ninja for TestNet

##### Those servers are provided freely by Nicolas Dorier (tips appreciated at 15sYbVpRh6dyWycZMwPdxJWD4xbfxReeHe) for the community, and should not be used in production environment, downtime and loss of wallet information should be expected. The expectation is that service providers host their own server privately.QBit Ninja depends on NBitcoin.Indexer which rely on Microsoft Azure Storage.C# developers are expected to use the nuget client package instead of developping a wrapper around this API.The goal of QBit Ninja is to take the heavy lifting of managing balances off the shoulder of application developers, while permitting them not to depend on potentially unreliable and untrusted third party like blockchain.info.
