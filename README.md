#[tailsjoin](https://github.com/tailsjoin/tailsjoin/wiki)
##Scripts to install [JoinMarket](https://github.com/chris-belcher/joinmarket), [libsodium](https://download.libsodium.org/doc/), and [Bitcoin Core](https://bitcoin.org/en/download) on the [Tails OS](https://tails.boum.org).

##WARNING: THE JOINMARKET DEV, CHRIS BELCHER, HAS DECIDED TO [ADD A DONATION](https://github.com/chris-belcher/joinmarket/commit/d74a02d6017a1c0006f2171f7e4456e525b5c4df) TO THE TUMBLER AND [REFUSES](https://reddit.com/r/joinmarket/comments/3q27ys/funding_development_of_joinmarket/) TO PROPERLY ALERT USERS. (IT'S ONLY [SUBTLY MENTIONED IN THE HELP MENU](https://github.com/chris-belcher/joinmarket/pull/272) FROM TUMBLER.PY). THE DEFAULT SETTING IS 1.5% BEING DONATED TO JOINMARKET DEV WHEN YOU RUN THE TUMBLER. 

##TO OPT-OUT YOU *MUST* RUN THE TUMBLER LIKE THIS:

    torify python tumbler.py --donateamount=0 <the rest of your options>

###Options for TAILS:

1. Run `tailsjoin.sh` on a minimal system without enough disk space to store the blockchain. This will use blockr.io (Coinbase) to check address balances and confirmed transactions. This is over Tor, of course, but still not optimal for privacy.

2. Run `tailsjoin-fullnode.sh` on either a system with enough disk space to hold the blockchain, or a minimal system with enough external storage to store the blockchain (50GB~). This is the suggested method for privacy and true control. 

---

###For a minimal system follow the steps below, or use the [detailed guide] (https://github.com/tailsjoin/tailsjoin/wiki/Detailed-Minimal-Setup-Guide) with pictures.

You must start Tails with "More options" setting in the beginning (Persistence is optional) and set an administrator password no matter which script you run.

All scripts are signed with my gpg key: [`44C5 398E A821 BB41 A0C0  7052 1B91 84DF 9E11 7718`](https://github.com/tailsjoin/tailsjoin/wiki/GnuPG-Key)

1. `cd /home/amnesia/Persistent` (optional)
2. `git clone https://github.com/tailsjoin/tailsjoin`
3. `cd tailsjoin`
4. `gpg --recv-keys 44C5398EA821BB41A0C070521B9184DF9E117718`
5. `gpg --verify tailsjoin.sh.asc tailsjoin.sh`
6. `./tailsjoin.sh`
    
Be aware, the script will prompt for the administrator password several times throughout.

After installation you will have to add `torify` to every command that does blockchain lookups. [Detailed explanation](https://github.com/tailsjoin/tailsjoin/commit/0b42441277dfe77bccfefe6075cb688c0b603e4a).

Examples:

    torify python wallet-tool.py <wallet_file>
    torify python sendpayment.py -N 4 <amount> <destination_address>

---

####[Simple send payment guide.](https://github.com/tailsjoin/tailsjoin/wiki/Send-Payment-Guide)

####[Detailed install and send payment guide.](https://github.com/tailsjoin/tailsjoin/wiki/Detailed-Minimal-Setup-Guide)

####[Orderbook Watcher Hidden Service](http://ruc47yiosooolrzw.onion/)

---

##Official JoinMarket Project Information:

IRC: `#joinMarket` on irc.freenode.net https://webchat.freenode.net/?channels=%23joinmarket

Bitcointalk thread: https://bitcointalk.org/index.php?topic=919116.msg10096563

Subreddit: https://reddit.com/r/joinmarket

Twitter: https://twitter.com/joinmarket

JoinMarket Donation address: `1AZgQZWYRteh6UyF87hwuvyWj73NvWKpL`

####[JOINMARKET OFFICIAL WIKI FOR DETAILED ARTICLES/GUIDES](https://github.com/chris-belcher/joinmarket/wiki)

---

The tailsjoin project has absolutely no affiliation with the Tails operating system, and no longer has any with JoinMarket. Although I have contributed to JoinMarket I no longer agree with the lead devs policy of hidden taxation. Therefore my morals keep me from supporting such a project. 

Tailsjoin is resources for end users to easily and safely anonymize their Bitcoin transactions using existing tools. If you appreciate my work here please teach someone you know how to use these tools or make someone smile.
