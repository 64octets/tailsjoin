# tailsjoin
## Script to install JoinMarket and dependencies on Tails OS.

You must start Tails with "More options" setting in the beginning (Persistence is optional) and set an administrator password.

The script is signed with my gpg key: [0x1B9184DF9E117718](https://github.com/tailsjoin/tailsjoin/wiki/GnuPG-Key)

    cd /home/amnesia/Persistent (optional)
    git clone https://github.com/tailsjoin/tailsjoin
    cd tailsjoin
    gpg --recv-keys 0x1B9184DF9E117718
    gpg --verify tailsjoin.sh.asc tailsjoin.sh
    ./tailsjoin.sh
    
Be aware, the script will prompt for the administrator password several times throughout.

After installation you will have to add `torify` to every [command](https://github.com/tailsjoin/tailsjoin/commit/0b42441277dfe77bccfefe6075cb688c0b603e4a) that does blockchain lookups:

    torify python wallet-tool.py <wallet_file>
    torify python sendpayment.py -P -N 4 <amount> <destination_address>

####[Send payment guide in wiki.](https://github.com/tailsjoin/tailsjoin/wiki/Send-Payment-Guide)

---

##JoinMarket info:

IRC Channel:
JoinMarket on irc.freenode.net
https://webchat.freenode.net/?channels=%23joinmarket

Bitcointalk thread:
https://bitcointalk.org/index.php?topic=919116.msg10096563

Subreddit:
www.reddit.com/r/joinmarket

Twitter:
www.twitter.com/joinmarket

Donation address:
1AZgQZWYRteh6UyF87hwuvyWj73NvWKpL

Wiki page for more detailed articles:
https://github.com/chris-belcher/joinmarket/wiki
