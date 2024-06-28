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

# how bitcoin stores transactions
## simple way
jadi -(20)-> reza\
reza -(10)-> ali\
reza -(10)-> ali2\

## bitcoin way
It tracks it's ledgers (coin)\
example:\
COIN -(1)-> jadi\
jadi -(1)-> reza\
reza -(1/4)-> x\
reza -(3/4)-> y


A coin is simply a gift card that is inchargable and Disposable

bitcoin has a programming language based on forth (stack based)

# bitcoin network
- peer to peer (nodes connected to some other nodes, like a graph)
- tcp and random topology (find new friends :\))
  - you wil need to seed note
  - others will start to forget you if you are not active for 3 hours
- flood or gossip protocol. you tell the people you know, the check and pass if checks are passed
  - latency can lead to different mempool, but mining will decide the ties (race condition)
- around 10k full chain nodes are 24/7 active
- there are also simplified payment verification nodes (SPV) or lightweight nodes the only >>>>>> headers, so only 100s of MBs instead of 100s of GBs


# bitcoin limitations
- created in 2009
- each block is 1MB, each TRX is 250 bytes -> each block contain 4K TRX only
- one block every 10 minutes -> 7 TPS (VISA handles around 2K TPS and can handle 10K TPS peak)
- cryptographic algorithm is ESDSA. some belive this will be broken during bitcoin lifespan
- solution? soft and hard forks


# store bitcoin secret keys
storing bitcoin is all about stroing secret keys

## wallet
uses base58 encoding
### what is base58
it uses numbers, uppercase english words and lowercase english words, and subtitutes the similar characters
for example, if in the address the letter "l" (lowercase L) exists, so it won't use "1" (one number)


## vanity address
create customize wallet address

# hot storage and cold storage
**cold** storage: **not** connected to internet
**hot** storage: connected to internet

## secret sharing
this mechanism helps users when they lose their secret key and want to for example: get their money.\
An example of that is 3 secret keys, and the transaction is done with 2 of them. that means, when 1 key is missed, we can do our transaction, and that 1 key is useless

## wallet or bank proofs
the wallets or banks try to prove their credit. this will happen in these ways

the banks report two numbers
- how much money currently have
- how much **potential** money currently have

they must have 3-10% of their potential money in order to keep order

### proof of reserve
the exchange or wallet website must prove that has enough money. An example of proof is sending a lot of money to it's another wallet and the users can check transactions in the network

### proof of liabilities
it uses [merkle tree](https://en.wikipedia.org/wiki/Merkle_tree). some people can check the proof with roothash. it uses this algorithm because the users does not want their data to be shared and visible to other

# mining
the sha256 hash of these
- previous block hash
- merkle tree of mempool TRXs (contains TRX for ourself)
- nounce
must be lower than the network difficulty level

## hardware
bitcoin uses sha256 hashing
CPU (20M), GPU(200M), FPGA(1G), ASIC(14G)
### FPGA
can program to compute only one thing

### ASIC


# pool
because the hash computation is very hard (even with ASIC), some organizations create a pool of users that work on finding a specifi nounce



# mining attacks
- forking attack (spending and then mining previous block)
- forking via bribery
- block withholding attacks = selfish mining
- blocklisting or punitive forking (announcing that you won't work on a chain if it contains blah blah)
- feather forking (just like punitive forking but just for a short period of time)


