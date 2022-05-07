# Vanilla JS Browser Wallet
A bare-bones bitcoin wallet for the base layer implemented in vanilla javascript

# How to use it
Go here: [https://supertestnet.github.io/vanilla-js-browser-wallet/wallet.html](https://supertestnet.github.io/vanilla-js-browser-wallet/wallet.html)

It should be pretty self explanatory, there's a send button, a receive button, and the homepage displays your balance and backup words (which you can hide after you write them down). That's all.

# Purpose
This wallet is intended for use by JS hackers who want to add a basic bitcoin wallet to their website or chrome extension. You can copy the code from here and use it elsewhere.

# Limitations

The fee estimator needs some work. I wrote a spec sheet that has me create a variable that incorporates the dust limit plus some extra data depending on how many inputs a transaction has and at some point I got that variable mixed up with the dust limit itself. I need to fix that because right now this mistake causes the transaction builder to set the transaction fee higher than what you selected.

When you start the wallet it is also kinda slow to display your balance and your first unused address. I use blockstream.info as a chain backend and it queries them every five seconds for a bunch of addresses -- at least 20 change addresses and 20 receive addresses (because I set a gap limit of 20) -- and when you start the wallet it won't show your balance until it's done with these queries. So be a little patient. Maybe I should add some sort of progress indicator.
