# Blockchain A-Z

> Notes on the course: [https://www.udemy.com/course/build-your-blockchain-az/](https://www.udemy.com/course/build-your-blockchain-az/)

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
- Even if we change the input text by one character, the hash changes completely - this is called the avalanche effect

### Requirements of a hashing algorithm

1. One-way

![https://i.imgur.com/rM6FFss.png](https://i.imgur.com/rM6FFss.png)

1. Deterministic: The same doc should always produce the same hash
2. Fast computation
3. **The avalanche effect** : This is v important - A tiny change in the doc should change the hash almost completely.
4. It must withstand collisions - Even in people, sometimes 1 in about 60 mil people have the  same fingerprint. Same thing for hashing algos - 64 bits - so its still limited, and the no of digital docs we create is unlimited - so there will be collisions, but its v rare and its tolerable. The algo needs to withstand **artificial collisions** - if someone finds a way to make 2 docs have the same hash for an algo then this is a problem, as then docs can be forged.