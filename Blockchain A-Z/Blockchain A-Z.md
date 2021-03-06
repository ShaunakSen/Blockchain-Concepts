# Blockchain A-Z

> Notes on the course: [https://www.udemy.com/course/build-your-blockchain-az/](https://www.udemy.com/course/build-your-blockchain-az/)
> 

# Blockchain Intuition

Each block in a blockchain is cryptographically linked to its previous block

The hash of a block is a function of its data, so of the data changes the hash changes. Since the next block refers to the this block by its hash, it will also know that the data has changed in this block 

![https://i.imgur.com/8Il0rPt.png](https://i.imgur.com/8Il0rPt.png)

### Understanding SHA256 Hash

The way that a fingerprint identifies a person, we want to have a digital fingerprint that will identify a document - This is what SHA256 (Secure Hash Algo, 256 is the no of bits it takes in memeory) does

The algorithm for SHA256 is open source

![https://i.imgur.com/m93aKKZ.png](https://i.imgur.com/m93aKKZ.png)

The hash is 64 bits long, It is a hexadecimal hash, consists of numbers in range **0-9, A,B,C,D,E,F**

As its a hexadecimal hash, each char reqs 4 bits, so 64 chars require 64 x 4 = 256 bits

This algorithm works for **anything digital -** video, audio, text, OS etc.

Tool to try out the SHA256 hash: [https://tools.superdatascience.com/blockchain/hash/](https://tools.superdatascience.com/blockchain/hash/)

A couple of things to note:

- The same data always produces the same hash
- Even if we change the input text by one character, the **hash changes completely** - this is called the **avalanche effect**

### Requirements of a hashing algorithm

1. One-way

![https://i.imgur.com/rM6FFss.png](https://i.imgur.com/rM6FFss.png)

1. Deterministic: The same doc should always produce the same hash
2. Fast computation
3. **The avalanche effect** : This is v important - A tiny change in the doc should change the hash almost completely.
4. It must withstand collisions - Even in people, sometimes 1 in about 60 mil people have the  same fingerprint. Same thing for hashing algos - 64 bits - so its still limited, and the no of digital docs we create is unlimited - so there will be collisions, but its v rare and its tolerable. The algo needs to withstand **artificial collisions** - if someone finds a way to make 2 docs have the same hash for an algo then this is a problem, as then docs can be forged.

## The Immutable Ledger

![https://i.imgur.com/SeyGPPU.png](https://i.imgur.com/SeyGPPU.png)

We saw the above architecture of the diagram already, lets see how it works in the real world

Say we want to buy a house, u pay the money and buy a house... But how do u know that u have the house? We get a title **deed** to the house and whoever has that deed has ownership, we have to take the deed to the govt and register the ownership - this is what makes that house ours

The govt writes this ownership down in a ledger - might be digital/physical books

This is all there is - a deed that u own and an entry (physical/digital) in some govt building - as u can imagine this is so prone to errors and crime. If only that entry is gone, you will lose the house!

Blockchain helps **fix** this

A very simple system is to simply store the entries in a blockchain and simply store that blockchain in a govt facility - say u make an entry and someone later tries to tamper with that entry, this will make all following blocks invalid as the hash of the current block will change and the cryptographic links wont work

So the hacker will have to change all the entries following our block, so the ledger is **immutable**

Here we see that even changing a simple blockchain stored in a central place, for a distributed one over a p2p nw this will be virtually impossible

This area of property ownership is a very practical use of blockchain

 

![https://i.imgur.com/fmTyBg1.png](https://i.imgur.com/fmTyBg1.png)

From the above diag we can see the scale of the problem, a huge number of high value transactions take place very month and if done without proper automation and security, errors are bound to creep in

> Physical tracking of any asset - wherever we are using ledgers, we can move to blockchain
> 

## Distributed p2p Network

In the blockchain we have studied so far, if we want to tamper an entry, changing an entry involves modifying **all following entries** which is cumbersome, sure, but still doable

Also consider that there is a system error, and a block gets modified, the cryptographic link will be broken, but we wont be able to restore the previous data

These problems are solved using a distributed p2p nw

1. We have a bunch of interconnected computes
2. The blockchain is copied across all computers
    
    ![https://i.imgur.com/PAxBssC.png](https://i.imgur.com/PAxBssC.png)
    
3. Anyone on their computer can modify this blockchain
4. Once a new block is added, this info is communicated through the nw and that block is added until **all the computers have that block** (the green one in the diagram below)
5. Lets say that some time passes and other blocks have been added to the network
    
    ![https://i.imgur.com/uvY3lqt.png](https://i.imgur.com/uvY3lqt.png)
    
6. Say someone tries to attack that entry and change it on one of the nodes (same goes for accidental modification). Also all the blocks following that will be invalid now
    
    ![https://i.imgur.com/jtqI6t6.png](https://i.imgur.com/jtqI6t6.png)
    
7. Now lets assume that this hacker has a decent amount of computation power and he goes ahead and recomputes the hashes of all the following blocks to make the chain valid. Now they have a valid tampered blockchain on that node
    
    ![https://i.imgur.com/gRJkzDp.png](https://i.imgur.com/gRJkzDp.png)
    
8. In this distributed p2p nw what's happening is that all the nodes are constantly checking their peers to see if their blockchains match up
9. So here the peers will see that the blockchain on that node does not match and would signal to that blockchain, and the hacked node would realize that its in the minority and would understand that its hacked and the modified blocks will be restored from the other nodes.
10. So the hacker cannot simply attack one computer, it will have to attack > 50% of the peers simultanously!
11. So the more the no of peers, more difficult is hacking into it
12. Also the data of people is represented only by some identifiers, so no one can actually see who made the transaction

So now we have seen 2 levels of security for the blockchain ??? hash cryptography ??? distributed p2p nw

## How mining works

Lets take an example of a hypothetical block

```bash
hash of current block = hashing_algo(block no, data, prev hash)
```

![https://i.imgur.com/pSxou1J.png](https://i.imgur.com/pSxou1J.png)

Now note that computing this hash is quite simple and in reality there is another field in a block called **NONCE (Number Used Only Once)**

![https://i.imgur.com/8gd29WT.png](https://i.imgur.com/8gd29WT.png)

```bash
hash of current block = hashing_algo(block no, nonce, data, prev hash)
```

This gives us more control as now we can change the hash value by manipulating the Nonce

We cant change the other params, but we can change the Nonce

Currently Nonce is 0

Also remember that even if we change Nonce slightly the hash will completely change due to the Avalanche effect

We are changing 1 bit of info, but the hash changes completely!

Remember also that the hash is a hexadecimal no, **but a number nevertheless, so we can do mathematical operations on it**

This means that there is an order to the hashes, some are smaller, some are larger

![https://i.imgur.com/A89HAiL.png](https://i.imgur.com/A89HAiL.png)

Now all miners are **given a target number - the miners have to find a hash which will be < than the target - this is done purely so that we can ensure that finding a valid hash is a computationally expensive problem**

A good way to think about the target is in terms of the leading 0s - so for example let us consider that the target we require has to have **at least 4 leading 0s**  - if lesser leading 0s that means that the number is > target and is not valid

Lets come back to the block example we had before with the block no, nonce, data, prev hash and current hash

```bash
hash of current block = hashing_algo(block no, nonce, data, prev hash)
```

Say we use nonce = 23 to compute a hash , its more than the target, we repeat for many iterations until we find a valid nonce that generates a hash < target, here its 5012

 

![https://i.imgur.com/GYVJFSD.png](https://i.imgur.com/GYVJFSD.png)

Note there is no pattern we can follow to smartly generate valid nonce, we just have to keep trying via brute force

The valid nonce found is commonly called "golden nonce"

Note that the hash generated now has 4 leading 0s and the miner can now add that block to the blockchain and gets a reward for his efforts

## The Byzantine Fault Tolerance

Imagine there are N (here say 4) generals who want to attack a castle. They can only win if the **majority can come to a consensus of what to do (attack/retreat).**

Among the generals there is one commander and there is also a traitor. The generals do not know who the traitor is (even the commander can be the traitor)

How to come up with a protocol that will help them come to a decsion

Algo: Look at the majority of the messages u get and decide action according to majority

Say main general issues order to attack (red one is the traitor)

![https://i.imgur.com/F6JdhEs.png](https://i.imgur.com/F6JdhEs.png)

The traitor of course conveys the wrong info:

![https://i.imgur.com/2yPKGXs.png](https://i.imgur.com/2yPKGXs.png)

But the other 2 broadcast the correct message that they received from the commander:

![https://i.imgur.com/TG3XUZn.png](https://i.imgur.com/TG3XUZn.png)

Now the commander of course attacks

Each of the true generals receive 2 correct msgs and 1 false msg, so they chose majority and attack

![https://i.imgur.com/axUa47U.png](https://i.imgur.com/axUa47U.png)

Lets now consider that the commander is the traitor

What he can do is tell 2 to attack and 1 to retreat

![https://i.imgur.com/HOfyMaK.png](https://i.imgur.com/HOfyMaK.png)

The other 3 generals simply relay what they heard from the general:

![https://i.imgur.com/MBKksHQ.png](https://i.imgur.com/MBKksHQ.png)

![https://i.imgur.com/68mcfvo.png](https://i.imgur.com/68mcfvo.png)

As we see here as well, each general picks the majority of the message received and as a result, they all come to a concensus

> Now the question is, to what level is this algorithm tolerant?
> 
- In case of 2 traitors, the algorithm fails
- **For it to work, more than 1/3 of the army cannot be traitors**

Level of tolerance ??? 1/3 or 33.33%

Similarly, in blockchain network, we need a protocol that makes it tolerant to a % of attackers

This is also used in systems which rely on info from multiple sensors, what if one sensor fails and it gives wrong info to main system - the system should be tolerant to such faults - this is used in airplanes, nuclear sys, rockets etc.