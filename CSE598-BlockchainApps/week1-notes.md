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
