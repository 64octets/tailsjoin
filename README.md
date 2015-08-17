#[tailsjoin](https://github.com/tailsjoin/tailsjoin/wiki)
##Scripts to install [JoinMarket](https://github.com/chris-belcher/joinmarket), dependencies, and/or  [Bitcoin](https://bitcoin.org/en/download)/[BitcoinXT](https://github.com/bitcoinxt/bitcoinxt) on the [Tails live OS](https://tails.boum.org).

###Options for Tails.

1. Run `tailsjoin.sh` on a minimal system without enough disk space to store an indexed blockchain.

2. Run `tailsjoincore.sh` on either a system with enough disk space to hold an indexed blockchain, or a minimal system with enough external storage to store an indexed blockchain (60GB~)

---

###For a minimal system follow the steps below, or use [this detailed guide.](https://github.com/tailsjoin/tailsjoin/wiki/Detailed-Minimal-Setup-Guide)

You must start Tails with "More options" setting in the beginning (Persistence is optional) and set an administrator password no matter which script you run.

The script is signed with my gpg key: [`44C5 398E A821 BB41 A0C0  7052 1B91 84DF 9E11 7718`](https://github.com/tailsjoin/tailsjoin/wiki/GnuPG-Key)

    cd /home/amnesia/Persistent (optional)
    git clone https://github.com/tailsjoin/tailsjoin
    cd tailsjoin
    gpg --recv-keys 44C5398EA821BB41A0C070521B9184DF9E117718
    gpg --verify tailsjoin.sh.asc tailsjoin.sh
    ./tailsjoin.sh
    
Be aware, the script will prompt for the administrator password several times throughout.

After installation you will have to add [`torify` to every command](https://github.com/tailsjoin/tailsjoin/commit/0b42441277dfe77bccfefe6075cb688c0b603e4a) that does blockchain lookups because the minimal setup uses blockr.io (Coinbase):

    torify python wallet-tool.py <wallet_file>
    torify python sendpayment.py -N 4 <amount> <destination_address>

---
#### * [Simple send payment guide.](https://github.com/tailsjoin/tailsjoin/wiki/Send-Payment-Guide)
#### * [Detailed install and send payment guide.](https://github.com/tailsjoin/tailsjoin/wiki/Detailed-Minimal-Setup-Guide)
#### * [Orderbook Watcher Hidden Service](http://ruc47yiosooolrzw.onion:62601/)
---

#### * Tailsjoin Donation Address: `1A2NeDroe7rzw1SWtqZJm3Los6HJMV1frb`

---

##Official JoinMarket Project Information:

IRC Channel:
JoinMarket on irc.freenode.net
https://webchat.freenode.net/?channels=%23joinmarket

Bitcointalk thread:
https://bitcointalk.org/index.php?topic=919116.msg10096563

Subreddit:
https://reddit.com/r/joinmarket

Twitter:
https://twitter.com/joinmarket

JoinMarket Donation address:
1AZgQZWYRteh6UyF87hwuvyWj73NvWKpL

Wiki page for more detailed articles:
https://github.com/chris-belcher/joinmarket/wiki
