## INTRO
PIRATE is the best of Zcash combined with the best of Monero. It's a forced Shielded-transactions (z-transactions) only blockchain, meant for completely anonymous transactions. PIRATE is mined into a transparent address, but can only go into a shielded address from there.
PIRATE is an independent blockchain built using Komodo Platform technology which is privacy transactions only blockchain. PIRATE is feature complete for its goal: complete anonymity.

## UPDATE 24/09/2018:

- PIRATE is now secured using dPoW, by only allowing the 64 Komodo Notary Nodes to do the t-transactions needed to secure the PIRATE blockchain.
- PIRATE's halving has been quintupled: instead of every 77777 blocks, PIRATE now halves every 388885 blocks.

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

## EXCHANGE
- none yet
- OTC in #trading #pirate in Komodo Discord - https://komodoplatform.com/discord

## STATUS
** Feature Complete **

## HOW TO CONTRIBUTE
- Securing network with Equihash Proof of Work (PoW).
- Making a z transactions only mining Pool.
- Listing PIRATE on your Centralised Exchange which means supporting z transactions for both withdraw/deposts.
- Creating a product or services using PIRATE.
- Testing, and reporting any bugs.


## FIND US:
Chat: Komodo Platform Discord - https://komodoplatform.com/discord
Forum/BTT: 


## DOCUMENTATION

#### Getting Started
To get started with you only need Komodo Platform daemon installed on your machine. You can either download the wallet from Komodo Platform website and use the bundled "komodod" and "komodo-cli" in it, or you can also compile it on your machine.
Installation instructions are available on Komodo Platform documentation website here: https://docs.komodoplatform.com/komodo/install-Komodo-manually.html

#### Connect to PIRATE blockchain
Command to run PIRATE blockchain and connect with the network:

```shell
./komodod -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=136.243.102.225
```

#### Update PIRATE
Make sure to be on dev branch to update PIRATE:

First stop current PIRATE, if running:

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
# Get wallet and blockchain info
./komodo-cli -ac_name=PIRATE getinfo


# Get wallet information
./komodo-cli -ac_name=PIRATE getwalletinfo


# Get mining information
./komodo-cli -ac_name=PIRATE getmininginfo


# Generate a new Z/Private address
./komodo-cli -ac_name=PIRATE z_getnewaddress


# To backup the private key of a z address
./komodo-cli -ac_name=PIRATE z_exportkey "zaddr"


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

## RESOURCES

#### Mining pool:
[https://pirate.komodostats.com/](https://pirate.komodostats.com/)

#### Website:
[https://pirate.black](https://pirate.black)

#### Explorer(s)
[http://pirate.explorer.dexstats.info](http://pirate.explorer.dexstats.info)

#### Richlist (regenerated each 60 minutes)
[https://dexstats.info/richlist.php?asset=PIRATE](https://dexstats.info/richlist.php?asset=PIRATE)
