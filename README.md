[Discord](https://komodoplatform.com/discord/) | [Twitter](https://twitter.com/piratechain) | [Telegram](https://t.me/piratechain/) | [Reddit](https://www.reddit.com/r/piratechain) | [BitcoinTalk](https://bitcointalk.org/index.php?topic=4979549.0)

## INTRO

PIRATE is the best of Zcash combined with the best of Monero.
It's a forced Shielded-transactions (z-transactions) only blockchain, meant for completely
anonymous transactions. PIRATE is mined into a transparent address, but can only go into a shielded address from there.
PIRATE is an independent blockchain built using the Komodo Platform assetchains. PIRATE is feature complete for its goal: complete anonymity.

## UPDATE 02/10/2018

- Agama wallet now supports PIRATE. Download [here](https://github.com/KomodoPlatform/Agama/releases/tag/multios-0.2.42c)
- PIRATE giveaway [now active!](https://gleam.io/jNfG4/pirate-our-rigs-24-hours-raffle-of-mining-rig-time) (until 05/10/2018)
- Vote for the official PIRATE logo! More info soon.
- piratepool.io now sends 0.5% fee to PIRATE development fund
- PIRATE's hashrate is 3 times **higher** than KMD!

## UPDATE 24/09/2018

- PIRATE is now secured using dPoW, by only allowing the 64 Komodo Notary Nodes to do the t-transactions needed to secure the PIRATE blockchain.
- PIRATE's halving has been quintupled: instead of every 77777 blocks, PIRATE now halves every 388885 blocks (chain start parameter remains the same).

Update of komodod is required! See below.

## PIRATE PROPERTIES

- Komodo Assetchain
- Independent blockchain
- Privacy/Shielded/z tx only chain. No transparent transactions possible on PIRATE chain.
- Probably has the most shielded coins of all other coins, even more than Zcash
- Block time aprox 60 seconds.
- Block reward halves:
  - every 388885 blocks
  - every 270 days
- Block reward of 1 satoshi will be reached in about 25 years.
- Total supply of around 200 million PIRATE
- CryptoConditions contracts not possible on this chain, as it is a z-tx only chain.
- Mining algorithm: Equihash PoW
- Alternatively can use Verushash PoW, but has to be used for a 100% PoW chain.
- TOR network supported.

## EXCHANGE

- OTC trading in Komodo Discord - [komodoplatform.com/discord](https://komodoplatform.com/discord)
- [tortuga.exchange](https://tortuga.exchange) coming Q1 2019
- Ticker symbol: ARRR

#### Buy PIRATE
- Visit #OTC Channel on Komodo Discord [https://discordapp.com/invite/53M27QD](https://discordapp.com/invite/53M27QD)
- Buy via Onboarding Page [https://dexstats.info/onboarding.php](https://dexstats.info/onboarding.php)

## STATUS / ROADMAP

PIRATE is feature complete and ready to use!

- Q1 2019
  - Centralized z-only KMD <-> PIRATE exchange Tortuga

## HOW TO CONTRIBUTE

- Listing PIRATE on your Centralised Exchange which means supporting z transactions for both withdraw/deposts.
- Create adoption by adding PIRATE to your service
- Testing, and reporting any bugs.

## DOCUMENTATION

#### Getting Started

Agama now supports PIRATE! Download the latest Agama [here](https://github.com/KomodoPlatform/Agama/releases/tag/multios-0.2.42c).  
To get started with PIRATE, you only need Komodo Platform daemon installed on your machine. You can either download the wallet from Komodo Platform website and use the bundled "komodod" and "komodo-cli" in it, or you can also compile it on your machine.
Installation instructions are available on Komodo Platform documentation website here: https://docs.komodoplatform.com/komodo/install-Komodo-manually.html

#### Connect to PIRATE blockchain
Command to run PIRATE blockchain and connect with the network:

```shell
./komodod -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=136.243.102.225
```

*NOTE: Although the `-ac_halving` above is still 77777, internally this number has been multiplied by 5.*

#### Update PIRATE
Make sure to be on komodo dev branch to update PIRATE:

First, stop current PIRATE if running:

```shell
cd ~/komodo/src
./komodo-cli -ac_name=PIRATE stop
```

Now update komodod:

```shell
cd komodo
git checkout dev
git pull
./zcutil/build.sh -j2
```

When done, run the command above to start PIRATE again.

#### Mine PIRATE blockchain

Use "-gen" and "-genproclimit=X" to enable mining. Replace X with the number of CPU threads you want to use for mining PIRATE.
For mining pool links, see end of page.

```shell
./komodod -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=136.243.102.225 -gen -genproclimit=4
```

#### Add seed node IPs

Add seed nodes IP for better network connectivity. Example starting assetchain with 2 seed node IP

```shell
./komodod -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=136.243.102.225 -addnode=78.47.205.239
```

#### Wallet commands

```shell
# Get (transparent) wallet and blockchain info
./komodo-cli -ac_name=PIRATE getinfo


# Get (transparent) wallet information
./komodo-cli -ac_name=PIRATE getwalletinfo


# Get mining information
./komodo-cli -ac_name=PIRATE getmininginfo


# Generate a new Z/Private address
./komodo-cli -ac_name=PIRATE z_getnewaddress


# To backup the private key of a z address
./komodo-cli -ac_name=PIRATE z_exportkey "zaddr"

# Get z balance (hidden funds don't show in transparent commands)
./komodo-cli -ac_name=PIRATE z_gettotalbalance

# To send mined coins to a z address
./komodo-cli -ac_name=PIRATE z_shieldcoinbase "fromaddress" "tozaddress" ( fee ) ( limit )

# Example 1:
./komodo-cli -ac_name=PIRATE z_shieldcoinbase "RHYDbB9ZtoqSaTvJqkCNd7EH9eLnvULSnr" "zcdYeSbZCnvcbKhUPMYWdMy9FVdgQ2y9fivhbWgCuPsbFJ5VycayAZwrgkC8dbyVZd1einoNjKBa8hsXy71B3aMNVpinvsa"

# Example 2 Combines all PIRATE in different t-addresses to 1 z-address:
./komodo-cli -ac_name=PIRATE z_shieldcoinbase "*" "zcdYeSbZCnvcbKhUPMYWdMy9FVdgQ2y9fivhbWgCuPsbFJ5VycayAZwrgkC8dbyVZd1einoNjKBa8hsXy71B3aMNVpinvsa"

# To send a transaction from your z address to another z address
./komodo-cli -ac_name=PIRATE z_sendmany "fromaddress" [{"address":... ,"amount":...},...] ( minconf ) ( fee )

# Example:
komodo-cli -ac_name=PIRATE z_sendmany "zcdYeSbZCnvcbKhUPMYWdMy9FVdgQ2y9fivhbWgCuPsbFJ5VycayAZwrgkC8dbyVZd1einoNjKBa8hsXy71B3aMNVpinvsa" '[{"address": "zcVHHtp5vTFDASaMoWXGYnPYq7n6xqwtYDFmN4F9UX4T88MscMJY9wQgyAMWpM4ttNXDyQHcFDGgegs3CBDQ9KNWvUXaaUA" ,"amount": 5.9999}]'
```

#### How to enable TOR settings for PIRATE

Just start Tor Browser as usual and use this command to start PIRATE blockchain:

```shell
./komodod \
-ac_name=PIRATE \
-ac_supply=0 \
-ac_reward=25600000000 \
-ac_halving=77777 \
-ac_private=1 \
-addnode=37.9.62.186 \
-addnode=136.243.102.225 \
-daemon \
-proxy=127.0.0.1:9150   # Connect through TOR SOCKS5 proxy \
-listen   # Accept connections from outside (default: 1 if no -proxy or -connect) \
-listenonion   # Automatically create Tor hidden service (default: 1) \
-maxconnections=25 \
# -onlynet=onion  # Optional. If you only want to connect to peers via Tor network. If enabled no clearnet/internet IPv4/IPv6 addresses will connect as peers.
```

Tested successfully on MacOS + Linux.
On Windows make sure to remove all backslashes and comments to make the above into one single command:

```shell
komodod.exe -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=37.9.62.186 -addnode=136.243.102.225 -daemon -proxy=127.0.0.1:9150
-listen -listenonion -maxconnections=25
```

Remove the command line parameter or change it accordingly.

I just tested PIRATE over TOR in the most simplest and easiest setup way possible. Bit more advanced users can find this help link very useful which describes setting up "bitcoind" with Tor settings:
[https://bitcoin.stackexchange.com/questions/70069/how-can-i-setup-bitcoin-to-be-anonymous-with-tor](https://bitcoin.stackexchange.com/questions/70069/how-can-i-setup-bitcoin-to-be-anonymous-with-tor)

Linux admins and PIRATE miners can also help by setting up Tor PIRATE nodes, and share on this forum your .onion address and port for your PIRATE peer.
Once we have good amount of .onion based PIRATE peers we can add them to "-addnode=" list, and can have more privacy added to PIRATE.

The Tor support request has been shared with Agama Wallet developers. Let's hope we get Tor Support in Agama Wallet soon. Once done, setting up Tor for a coin or assetchain would be easier.

### Mining pools:
 - **Pool 1 (1% mining fee):** [https://piratepool.io/](https://piratepool.io/)
 - **Pool 2 (0% mining fee):** [https://arrr.pool-mining.xyz/](https://arrr.pool-mining.xyz/)
 - **Pool 3 (1% mining fee):** [https://piratechain.org/](https://piratechain.org/)
 - **Pool 4 (0% mining fee):** [https://theminingpoolstratum.selfip.com/pirate/public/](https://theminingpool.online/)
 
Getting Started guide by webworker01: [piratepool.io/getting_started](https://piratepool.io/getting_started)

### Mining Calculator:
[https://www.crypto-coinz.net/coin-info/?203-Pirate-ARRR-Equihash-calculator/](https://www.crypto-coinz.net/coin-info/?203-Pirate-ARRR-Equihash-calculator/)

#### Developers (PIRATE Github)

[https://github.com/PirateNetwork/](https://github.com/PirateNetwork/)

#### Explorer

[http://pirate.explorer.dexstats.info](http://pirate.explorer.dexstats.info)

#### Richlist (regenerated each 60 minutes)

[https://dexstats.info/richlist.php?asset=PIRATE](https://dexstats.info/richlist.php?asset=PIRATE)

### Articles

- **PIRATES of Komodo Platform:** [https://medium.com/@satindergrewal/pirates-of-komodo-platform-cdc991b424df](https://medium.com/@satindergrewal/pirates-of-komodo-platform-cdc991b424df)
- **PIRATE is all about privacy & nothing about piracy:** [https://medium.com/@satindergrewal/pirate-is-all-about-privacy-nothing-about-piracy-2962eb5bb818](https://medium.com/@satindergrewal/pirate-is-all-about-privacy-nothing-about-piracy-2962eb5bb818)
 - **Post in Spanish "PIRATE, the most anonymous cryptocurrency in the world":** [https://steemit.com/spanish/@thewalker/pirate-la-criptomoneda-mas-anonima-del-mundo](https://steemit.com/spanish/@thewalker/pirate-la-criptomoneda-mas-anonima-del-mundo)
 - **PIRATEchain — Why we need anonymity:** [https://medium.com/@seko1900/piratechain-why-we-need-anonymity-4aa7a7d854ef](https://medium.com/@seko1900/piratechain-why-we-need-anonymity-4aa7a7d854ef)

