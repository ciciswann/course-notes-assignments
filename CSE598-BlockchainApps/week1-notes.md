# Week 1 Notes

### Introduction to Blockchain Technology 
*Objective 1: Describe the basic blockchain data structure* \
*Objective 2: Identify key factors accompanying the basic blockchain data structure*

* What is the blockchain?
* How does blockchain technology work?
* What is blockchain technology good for?
* An analogy: Google documents (changelog - who, what, when)
* From changelog to blocks of information

#### Blockchain Data Structures
* For each block - one section is for data and one is for the block header (gives structure to that specific block)
* In data section, transactions are stored 
* In header - timestamp, hash of previous block header, hash of transactions, nonce
* Timestamp - the time when the block was created 
* Hash function - takes an input of information and transforms it into a unique sequence of characters, sequence is always of the same length
* Hash of Transactions - Take transactions and process through hash function to come up with unique identifier
* Just knowing the identifier, you won't be able to know the input, but if you put the same input in it will always output the same identifier
* Blocks are connect by every subsequent block including the hash of the previous block header hash in its block header
* Changing a transaction in a block also changes the block header

#### Accompanying Factors
* **Mining** - mechanism used in most cryptocurrencies to systematically give rights to add data to the blockchain
* Five mining actions - validate transactions, propogate transactions, validate blocks, propogate blocks, store the data
* Mining incentives - giving the miner of each block (the node that puts the block on the blockchain) a block reward, giving the miner transaction fees which are paid by those conducting the transactions
* Proof-of-work mining 
* Proof of Work (PoW) - mining allows us to give the right to add the next block on the blockchain by creating a game that requires miners to solve a complex mathematical puzzle (produce work)
* Mining Difficulty Rate - can be thought of as the hash of the blcok header must contain a certain number of 0's at the beginning
* Miners adjust the value of the Nonce field, located in the block header, so that the hash of the block header will be less than or equal to the difficulty target of the network
* **Consensus** - the ability for all honest participants to come to an agreement over a single truthful version of the blockchain in a trustless manner
* Consensus algorithm - is the algorithmic process in which a blockchain network achieves consensus
* The current state is derived from transactions on the blockchain but is not stored on the blockchain

### Benefits of Blockchain Technology
* Transparency - available to all other nodes/apps connected to those blockchains
* Traceability - information is in header, it allows network participants to track the movement of a specific item of interest throughout the supply chain
* Security - all information is already stored in blockchain without need to provide additional authentication
* Immutability 
* Availability - highly redundant and distributed system of nodes
* Cost-saving - no need for additional parties to act as a source of trust, save time and external involvement

### Blockchain Applications
* Established and emerging - currency|payments, smart contracts, supply chain, governance, file storage
* smart contracts - automating work flows without waiting for anyone
* governance - voting systems, unique id valid on the blockchain
* file storage - in response to growth of data
* Internet of Things (IoT) - help with security 
* Identity management - unique id on the blockchain as a digital signature
* Data Management - info can be verified and traced
* Land title registration - making sure title can't be altered (immutability and traceability)
* Stock Trading 

### Blockchain Ecosystem
* Health, Government, IoT, Finance, Real Estate, Cross-Industry, Legal
