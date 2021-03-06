# Mastering Bitcoin

Unlike traditional currencies, bitcoin are entirely virtual. There are no physical coins or even digital coins per se. The coins are implied in transactions that transfer value from sender to recipient. Users of bitcoin own keys that allow them to prove ownership of bitcoin in the bitcoin network. With these keys they can sign transactions to unlock the value and spend it by transferring it to a new owner. Keys are often stored in a digital wallet on each user’s computer or smartphone. Possession of the key that can sign a transaction is the only prerequisite to spending bitcoin, putting the control entirely in the hands of each user.

Bitcoin is a distributed, peer-to-peer system. As such there is no “central” server or point of control. Bitcoin are created through a process called “mining,” which involves competing to find solutions to a mathematical problem while processing bitcoin transactions. Any participant in the bitcoin network (i.e., anyone using a device running the full bitcoin protocol stack) may operate as a miner, using their computer’s processing power to verify and record transactions. Every 10 minutes, on average, someone is able to validate the transactions of the past 10 minutes and is rewarded with brand new bitcoin. Essentially, bitcoin mining decentralizes the currency-issuance and clearing functions of a central bank and replaces the need for any central bank.

The bitcoin protocol includes built-in algorithms that regulate the mining function across the network. The difficulty of the processing task that miners must perform is adjusted dynamically so that, on average, someone succeeds every 10 minutes regardless of how many miners (and how much processing) are competing at any moment. The protocol also halves the rate at which new bitcoin are created every 4 years, and limits the total number of bitcoin that will be created to a fixed total just below 21 million coins. The result is that the number of bitcoin in circulation closely follows an easily predictable curve that approaches 21 million by the year 2140. Due to bitcoin’s diminishing rate of issuance, over the long term, the bitcoin currency is deflationary. Furthermore, bitcoin cannot be inflated by “printing” new money above and beyond the expected issuance rate.

## History of Bitcoin

Bitcoin was invented in 2008 with the publication of a paper titled “Bitcoin: A Peer-to-Peer Electronic Cash System,”1 written under the alias of Satoshi Nakamoto (see Appendix A). Nakamoto combined several prior inventions such as b-money and HashCash to create a completely decentralized electronic cash system that does not rely on a central authority for currency issuance or settlement and validation of transactions. The key innovation was to use a distributed computation system (called a “Proof-of-Work” algorithm) to conduct a global “election” every 10 minutes, allowing the decentralized network to arrive at consensus about the state of transactions. This elegantly solves the issue of double-spend where a single currency unit can be  spent twice. Previously, the double-spend problem was a weakness of digital currency and was addressed by clearing all transactions through a central clearinghouse.

The bitcoin network started in 2009, based on a reference implementation published by Nakamoto and since revised by many other programmers. The implementation of the Proof-of-Work algorithm (mining) that provides security and resilience for bitcoin has increased in power exponentially, and now exceeds the combined processing power of the world’s top supercomputers. Bitcoin’s total market value has at times exceeded $20 billion US dollars, depending on the bitcoin-to-dollar exchange rate. The largest transaction processed so far by the network was $150 million US dollars, transmitted instantly and processed without any fees.

Satoshi Nakamoto withdrew from the public in April 2011, leaving the responsibility of developing the code and network to a thriving group of volunteers. The identity of the person or people behind bitcoin is still unknown. However, neither Satoshi Nakamoto nor anyone else exerts individual control over the bitcoin system, which operates based on fully transparent mathematical principles, open source code, and consensus among participants. The invention itself is groundbreaking and has already spawned new science in the fields of distributed computing, economics, and econometrics.

Satoshi Nakamoto’s invention is also a practical and novel solution to a problem in distributed computing, known as the “Byzantine Generals’ Problem.” Briefly, the problem consists of trying to agree on a course of action or the state of a system by exchanging information over an unreliable and potentially compromised network. **Satoshi Nakamoto’s solution, which uses the concept of Proof-of-Work to achieve consensus without a central trusted authority, represents a breakthrough in distributed computing and has wide applicability beyond currency. It can be used to achieve consensus on decentralized networks to prove the fairness of elections, lotteries, asset registries, digital notarization, and more.**

Bitcoin is a protocol that can be accessed using a client application that speaks the protocol. A “bitcoin wallet” is the most common user interface to the bitcoin system, just like a web browser is the most common user interface for the HTTP protocol. There are many implementations and brands of bitcoin wallets, just like there are many brands of web browsers (e.g., Chrome, Safari, Firefox, and Internet Explorer). And just like we all have our favorite browsers (Mozilla Firefox, Yay!) and our villains (Internet Explorer, Yuck!), bitcoin wallets vary in quality, performance, security, privacy, and reliability. There is also a reference implementation of the bitcoin protocol that includes a wallet, known as the “Satoshi Client” or “Bitcoin Core,” which is derived from the original implementation written by Satoshi Nakamoto.

## Quick start - Alice example

When Alice runs Mycelium for the first time, as with many bitcoin wallets, the application automatically creates a new wallet for her. The most important part of this screen is Alice’s bitcoin address. On the screen it appears as a long string of letters and numbers: 1Cdid9KFAaatwczBwBttQcwXYCpvK8h7FK.

*Bitcoin addresses start with a 1 or 3. Like email addresses, they can be shared with other bitcoin users who can use them to send bitcoin directly to your wallet. There is nothing sensitive, from a security perspective, about the bitcoin address. It can be posted anywhere without risking the security of the account. Unlike email addresses, you can create new addresses as often as you like, all of which will direct funds to your wallet. In fact, many modern wallets automatically create a new address for every transaction to maximize privacy. A wallet is simply a collection of addresses and the keys that unlock the funds within.*

Alice is now ready to receive funds. Her wallet application randomly generated a private key (described in more detail in “Private Keys”) together with its corresponding bitcoin address. At this point, her bitcoin address is not known to the bitcoin network or “registered” with any part of the bitcoin system. Her bitcoin address is simply a number that corresponds to a key that she can use to control access to the funds. It was generated independently by her wallet without reference or registration with any service. In fact, in most wallets, there is no association between the bitcoin address and any externally identifiable information including the user’s identity. Until the moment this address is referenced as the recipient of value in a transaction posted on the bitcoin ledger, the bitcoin address is simply part of the vast number of possible addresses that are valid in bitcoin. Only once it has been associated with a transaction does it become part of the known addresses in the network.

**Bitcoin transactions are irreversible**. Most electronic payment networks such as credit cards, debit cards, PayPal, and bank account transfers are reversible.

Before Alice can buy bitcoin from Joe, they have to agree on the exchange rate between bitcoin and US dollars. This brings up a common question for those new to bitcoin: “Who sets the bitcoin price?” The short answer is that the price is set by markets.

Bitcoin, like most other currencies, has a floating exchange rate. That means that the value of bitcoin vis-a-vis any other currency fluctuates according to supply and demand in the various markets where it is traded.

There are hundreds of applications and websites that can provide the current market rate. Here are some of the most popular:

- [https://coincap.io/](https://coincap.io/)

Alice has decided to convert $10 US dollars into bitcoin, so as not to risk too much money on this new technology. She gives Joe $10 in cash, opens her Mycelium wallet application, and selects Receive. This displays a QR code with Alice’s first bitcoin address.

Joe then selects Send on his smartphone wallet and is presented with a screen containing two inputs:

- A destination bitcoin address
- The amount to send, in bitcoin (BTC) or his local currency (USD)

Joe now has Alice’s bitcoin address set as the recipient. Joe enters the amount as $10 US dollars and his wallet converts it by accessing the most recent exchange rate from an online service. **The exchange rate at the time is $100 US dollars per bitcoin, so $10 US dollars is worth 0.10 bitcoin (BTC), or 100 millibitcoin (mBTC)**

Joe then carefully checks to make sure he has entered the correct amount, because he is about to transmit money and mistakes are irreversible. After double-checking the address and amount, he presses Send to transmit the transaction. Joe’s mobile bitcoin wallet constructs a transaction that assigns 0.10 BTC to the address provided by Alice, sourcing the funds from Joe’s wallet and signing the transaction with Joe’s private keys. This tells the bitcoin network that Joe has authorized a transfer of value to Alice’s new address. As the transaction is transmitted via the peer-to-peer protocol, it quickly propagates across the bitcoin network. In less than a second, most of the well-connected nodes in the network receive the transaction and see Alice’s address for the first time.

Meanwhile, Alice’s wallet is constantly “listening” to published transactions on the bitcoin network, looking for any that match the addresses in her wallets. A few seconds after Joe’s wallet transmits the transaction, Alice’s wallet will indicate that it is receiving 0.10 BTC.

At first, Alice’s address will show the transaction from Joe as “Unconfirmed.” This means that the transaction has been propagated to the network but has not yet been recorded in the bitcoin transaction ledger, known as the blockchain. To be confirmed, a transaction must be included in a block and added to the blockchain, which happens every 10 minutes, on average. In traditional financial terms this is known as clearing.

Alice is now the proud owner of 0.10 BTC that she can spend. In the next chapter we will look at her first purchase with bitcoin, and examine the underlying transaction and propagation technologies in more detail.

# Blockchain 101

> Notes on [https://academy.101blockchains.com/](https://academy.101blockchains.com/)

Blockchain is an **open, distributed ledger** that can record transactions bw 2 parties **efficiently and in a verifiable and permanent way**

It is:

- an open source system
- distributed: everyone (all the network participants) has a copy of the truth; this is different from traditional banking systems where there is a central entity
- It is based on a ledger (place where transactions are recorded) - we store a transaction in a blockchain. We have 2 distinct parties who might not know or trust one another but they can transact securely and without the need of any intermediary.
- It is permanent: once transaction is validated, then it is immutable

![https://i.imgur.com/Jp2YQ0n.png](https://i.imgur.com/Jp2YQ0n.png)

The nodes actually work together to make sure that the transaction is valid and that there is no double spending/copying. For instance if we want to send a document of the ownership of a house to someone we want to make sure that there are no copies and the doc is unique. Also when we transfer money, it should not get replicated. This is taken care of by the nodes

Once this is verified the block is added to the chain, and connected to the other existing blocks

![https://i.imgur.com/k8a9N4O.png](https://i.imgur.com/k8a9N4O.png)

In decentralized system, we have multiple control entities (servers) and the data is shared among these servers

The clients are connected to only one of these servers

So if that server goes down, all clients connected to that server will go out of sync

In distributed nw we have some special servers and the data is shared bw all nodes. The clients are not connected to any particular server

If a server goes down, the nodes can connect to any of the other nodes

At any time a node has access to the latest updated info in the nw

## Benefits of blockchain

1. Immutability; Once transaction is validated and the block is connected and the chain is created by cryptographically hashed links, the data cannot ever be changed

    But if we make the mistake also that mistake is immutably written in blockchain nut we can make changes to remedy mistakes

2. Shared and distributed
3. Decentralized: No single pt of failure; everytime a node get out of the system and returns it can always synchronize itself with the other nodes
4. Secure as no single pt of failure; 
5. We can increase nw capacity
6. P2P nw so no need of intermediaries so execution of transactions is much faster