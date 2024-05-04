link of [source](https://www.youtube.com/playlist?list=PL-tKrPVkKKE1gLxAL-56H-XR-fTapqofC)



# mem pool
- contains data such as:
    - transaction
    - timestamp
    - sign: meaming the coin provider sign for example: X gave coin C to Y
    - hash of transaction informations

# block
- creates when a node convert their mem pool record into a block
- each block stores its previous block hash



# node
- we have some nodes that each of them has:
    - mem pool
    - chain of blocks

# how transaction happens (in BTC)
- a node create a transaction record (TRX, TS, sign)
- stores in it's mem pool
- broadcast this transaction to all nodes
- all nodes store transaction in their mem pool

 
# common attacks

## double spend
Double-spending is a fundamental flaw in a digital cash protocol in which the same single digital token can be spent more than once

## sybil attack
A Sybil attack uses a single node to operate many active fake identities (or Sybil identities) simultaneously, within a peer-to-peer network

### how to stop it
#### POW (proof of work)
- the process of create transaction must be a very hard work
- bulletproof cryptography (difficult to compute, parametrized cost, trivial to verify)
- trustless system for annonymous participants
- concept of nounce value
- longest is the best (why? most POW)
- halving every 21000 blocks (4 years)
  - for xample: if the prize is 12.5 BTC, the next 4 years the prize will be 6.25 BTC
- will finish around 2140 with 21M BTC
- 51% attack
- cost of mining

must create a hash that for example:
- last three characters must be 0
- first character must be 0 (in BTC)
therefore, every mem pool has a nounce value

### nounce
a variable that can be set by node in order to create hash from mem pool
with this value, when the node wants to create has and this hash does not provide
the conditions, it can use the nounce value and change it in order to achive the required has

### what is mining
- looks in the mem pool
- adds a transaction of 12.5 BTC to it's public key
- adds a nounce value
- runs sha256 on all of them
- the value must be lower than hardnees of network

#### what if the more than one node founds a required hash
the transaction accepts for the blockchains that length of blocks is larger




# DOS
Denial-of-Service (DoS) Attack 
A denial-of-service attack restricts access to a computer or network in order to prevent intended users from using it. DoS attacks have become one of the go-to tools hackers employ in order to disturb the normal operation of computer-based services. One of the most effective approaches to completing such an attack is through a distributed approach. 