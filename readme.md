
==================


[OpenMarket](http://104.236.98.130:4568/) &mdash; A free, decentralized bitcoin-based marketplace.
==========
![](http://img.shields.io/version/0.0.3.png?color=green)

**Currently alpha testing on the bitcoin test network**

[OpenMarket](http://104.236.98.130:4568/) is an open-source, [decentrally-hosted](http://104.236.98.130:4568/network) marketplace, like amazon or etsy, where you can sell anything in exchange for bitcoin. 

The network and website uses the [raft protocol](https://raftconsensus.github.io/), and is hostable by any seller running software installed from this page. Buyers do not have to install anything; they can just type a [URL](http://104.236.98.130:4568/) into their browser.

It comes with a local-only, integrated [BitcoinJ](https://github.com/bitcoinj/bitcoinj)-based [Bitcoin wallet](http://github.com/tchoulihan/bitmerchant) so you can immediately start accepting payments for items without having to go through an intermediary service like coinbase or bitpay. This is the first fully decentralized bitcoin marketplace.

To see what its all about, check out a sample testing [OpenMarket website](http://104.236.98.130:4568/).

Suggest features or post bugs [here](https://github.com/tchoulihan/openmarket/issues/), or on the subreddit [r/openmarket_net](http://www.reddit.com/r/openmarket_net).

## Features include
* A complete web store akin to etsy including product reviews, ratings, wishlists, shipping tracking urls, feedback, categories, etc.
* A decentralized [raft-based](https://raftconsensus.github.io/) database, built atop [rqlite](https://github.com/otoolep/rqlite). 
* A fully portable webservice and website built with java [Spark](https://github.com/perwendel/spark). *No web server required*
* An offline bitcoin [wallet](http://github.com/tchoulihan/bitmerchant) that uses [BIP70](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki). 


## Screenshots:
<img src="http://i.imgur.com/dwqxaaL.png">
<img src="http://i.imgur.com/5BX8h5R.png">
<img src="http://i.imgur.com/xd40ucL.png">
<img src="http://i.imgur.com/ckDwi77.png">
<img src="http://i.imgur.com/0c584RB.png">


## Installation (only necessary for sellers)
### Requirements
- Java 8
- Go (version at least 1.4) 
  - [GVM](https://github.com/moovweb/gvm) is the best way to install go.
- If behind a router, make sure ports 4566-4570 are correctly forwarded to your local ip address.

Download the jar, located [here](https://github.com/openmarket/openmarket/releases/download/0.0.3/openmarket.jar)

To help test, use this command to join an existing test node that uses the bitcoin testnet:
<pre>java -jar openmarket.jar -testnet -join 104.236.98.130:4570</pre>

General usage:
<pre>java -jar openmarket.jar [parameters]</pre>
<pre>parameters:
 -deleteDB     : Delete the sqlite DB before running.(WARNING, this deletes
                 your wallet)
 -join VAL     : Startup OpenMarket joining a master nodeIE, 127.0.0.1:4001
 -loglevel VAL : Sets the log level [INFO, DEBUG, etc.]
 -port N       : Startup your webserver on a different port(default is 4567)
 -rqlport N    : Startup rql on a different port(default is 4570)
 -testnet      : Run using the Bitcoin testnet3, and a test DB
 -uninstall    : Uninstall OpenMarket.(WARNING, this deletes your wallet)


</pre>

A browser window will load the page at http://localhost:4567/, and make sure you complete the signup from there.

## Building from scratch

To build OpenMarket, run the following commands:
```
git clone https://github.com/openmarket/openmarket
cd openmarket
chmod +x deploy.sh

# This script does a git pull, maven install, and java -jar command
./deploy.sh -testnet -join 104.236.98.130:4570
```

and access http://localhost:4567/

## Support 
If you'd like to help fund me to keep developing openmarket, you can either post bounties for desired features [on BountySource](https://www.bountysource.com/trackers/12711596-tchoulihan-openmarket), or donate directly here:

[bitcoin:17N2wDi8Y6Cnrnrbzq5JsRcdjnW9DVyVhL](bitcoin:17N2wDi8Y6Cnrnrbzq5JsRcdjnW9DVyVhL)

![bitcoin:17N2wDi8Y6Cnrnrbzq5JsRcdjnW9DVyVhL](http://i.imgur.com/87N3QWu.png)

## Bugs and feature requests
Have a bug or a feature request? If your issue isn't [already listed](https://github.com/tchoulihan/openmarket/issues/), then open a [new issue here](https://github.com/tchoulihan/openmarket/issues/new).

## Contributing
Start with getting familiar with the [schema](http://ondras.zarovi.cz/sql/demo/?keyword=openmarket) first, then create some issues and we can start working on them. 

## Thanks
* Special thanks to Mike Hearn and Andreas Schildbach for their assistance with BIP70 and refunding orders.

## Feature requests / todos
* Work out some reliability issues with nodes going down in raft 

