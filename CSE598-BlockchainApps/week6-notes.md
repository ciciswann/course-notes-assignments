# Week 6 Notes

### Byzantine Generals Problem
* BGT 
  * communicating only by messenger, the generals must agree upon a common battle plan
  * one or more of them may be traitors who will try to confuse the others
  * the problem is to find an algorithm to ensure that the loyal generals will reach agreement
* A problem common to any computer system that relies on the ability to come to consensus on a decision over an unreliable and distributed communication/computer network
* extremely relevant to blockchain tech
* The generals represent the nodes within a computer system
* traitors represent faulty nodes
* messages corrupted during transport between the generals represent faulty communication channels
* The goal
  * design an algorithm/consensus protocol that guarantees two conditions
  * condition a
    * all loyal generals decide on the same plan of action:
      * in every scenario, all loyal generals will carry out the plan of action the algorithm specifies for that scenario
      * any and all traitorous generals may carry out any plan they wish regardless of what the algo suggests
      * regardless of what the traitorous generals do the algo must guarantee this condition
  * condition b
    * a small number of traitors cannot cause the loyal generals to adopt a bad plan:
      * unlike condition a, this condition is hard to formalize with respect to the definition of what a bad plan is
* algo guarantees
  * let v(i) be the information communicated by the ith general
  * condition A will achieved if each general uses the same method when combining the information
  * decision choice is limited to attack or retreat
  * conditon B can be achieved by each loyal general following the majority decision 
* Is there a key assumption being made in this solution? 
  * all loyal generals reveive the same values v(1),...,v(n)
* additional reqs
  * 1 - any two loyal generals use the same value of v(i)
  * 2 - if the ith general is loyal, then the value that he sends must be used by every loyal general as the of v(i)
* Reduction to Byzantine Generals Problem
  * Restrict our consideration of the problem to how a single general sends his value to the others
* A general sending orders to subordinates
  *  IC1: all loyal lieutenants obey the same order
  *  IC2: if the commanding general is loyal then every loyal lieutenant obeys the order he sends
  *  IC1 and IC2 are known as the interactive consistency conditions
  *  Note: if the commanding general is loyal then IC2 implies IC1
  *  To solve the original problem, the ith general sends his value v(i) using a solution to the BGP while considering the other generals as lieutenants

### Proof of Work Applied to the Byzantine Generals Problem
* Goal of finding an algorithm that... allows a deventralized network to come to consensus, guarantees two properties (all loyal generals decide upon same plan of action, small amount of traitors cannot cause loyal generals to adopt a bad plan)
* Reduce the problem to how a single node communicates his information
* Proof-of-Work Consensus Algorithm
  * probabilistic solution to BGP - probability of a malicious node generating an alternate history quicker than honest history decreases per added block
* Abstract Example
  * Byzantine generals will agree on a specific PoW problem, the generals begin solving the PoW problem, the general who solves the problem send messengers to the other generals, when a general receives a block he will independently verify the solution and incorporate it into his block if it is valid, as the process continues and more generals solve the PoW problem the chain grows
* Consensus Process Outcome
  * Generals can get a probability of how many other nodes are also in agreement with them (result of being able to calculate the time it takes for block production for entire chain they believe to be the honest plan)
  * PoW prevents conflicting signals
    * generals build PoW blocks on top of each other
    * Essentially seal/vote for info in parent block

### Combinatorics Applied to the Byzantine Fault Tolerance
* Nakamoto consensus
* even if there is a malicious node, it will most likely not make it to the chain

### Proof-of-Stake
* Consensus Algorithms (public and decentralized blockchain networks)
  * need source of randomness or pseudo-randomness to select miner
  * miner adds next block to blockchain
  * block is generally proportional to limiting economic resource
* Proof of Work
  * randomness comes from miners guessing different nonces
    * search for valid block header hash
    * computational power is the limiting economic resource
  * not the only consensus algo
  * computational power not always the limiting economic resource
* Intro to PoS
  * consensus algo that chooses block producer based on proportional economic stake
  * randomness derived from within protocol
  * chain-based
  * byzantine fault tolerance proof of stake 
* Chain-based PoS
  * Protocol chooses block for next block producer to point to
  * Protocol randomly chooses block producer to produce during the specified time period (based on proportional econ. stake)
  * During this time, block producer must produce a valid block - must point to the previous block chosen by the protocol
  * Block producer gets rewarded for producing a valid block
* Byzantine Fault Tolerance PoS
  * Protocol chooses block for next block producer to point to
  * Protocol randomly chooses block proposer to produce during specified time period
  * block proposer must produce a block during that time
  * validity of proposed block voted on - valid if two-thirds or more of votes say the block is valid
  * Block proposer rewarded  
* Nothing at Stake problem 
  * owning tokens to stake will not disincentivise bad behavior
  * major security concern in PoS

### Delegated Proof-of-Stake
* Algors that specify a group of actors that may participate in the consensus process - may decrease latency, increase reliability
  * will lost aspects of the intrinsic decentralization found in protocols that use open-participation consensus algos
* DPoS
  * consensus algorithm in which those with a stake in the network elect block procedures to participate in the consensus process
    * differs from traditional PoS in which those with a stake in the network are the block producers
    * Dan Larimer in 2013 for BitShares
  * Two main components: process by which block producers get elected, process by which producers produce blocks 
* BitShares implementation - election
  * those who want to be delegated as a block producer - register their public key with the network
  * those with BTS token vote
  * The top 101 block producers with the most votes from the network are the designated block producers
* Production
  * set of block prod get ordered such that each is allowed one time slot to produce
  * block producers produce valid blocks within their designated time slot
* Other - consensus chain rule - the longest valid chain with the highest witness participation rate
* electing delegates to decide on other properties of the network such as block size, block time interval, number of delegates
* Transactions as Proof of Stake (TaPoS) - each trans. will need to include the hash of the last valid block - build long chains - long-range attacks
* The participation rate is calculated by computed the expected number of blocks produced divided by the actual number of blocks produced within a certain period of time


### Practical Byzantine Fault Tolerance
* From public to permissioned blockchains
* consensus algorithms for open and public blockchains:
  * defenses against sybil attacks
  * aligning incentives (due to voluntary mining)
  * latency issues
* consensus algos for permissioned blockchains:
  * nodes within network identified, trusted, and verified
  * often direct connection made between all/most nodes - comm. latency is minimized  
* Practical Byzantine Fault Tolerance
  * 1999
  * classic consensus algo designed for asynchronous environments (distributed internet applications, now used for blockcain networks)
  * byzantine failure model - additional assumption of independent node failures
  * requires minimum of 3f+1 nodes - provides safety and liveness for up to f faulty nodes
  * a form of **state machine replication** - the state machine is replicated ac ross different nodes in a distributed system, each node maintains a copy of the state and implements operations
* PBFT how it works
  * moves thru phases called views - numbered consecutively, one node is denoted as primary, others are backups
  * a client sends a request to invoke a service operation to the primary
  * the primary multicasts the requests to the backups
  * all nodes execute the request and send a reply to the client
  * the client waiting for f+1 replies from different replicas with the same result - the result of the operation 
* Blockchain Implementation
  * nodes connected in distributed network
  * can submit a transaction to any of the nodes
  * primary node verifies and orders the propagated transaction 
  * nodes receive the block and proceed as follows:
    * every node executes the transactions within the block in order and verifies their validity
    * once all transactions are successfully executed, each node calculates the hash of the block
    * nodes broadcast the block hash to all the other nodes
    * once a node receives and confirms two-thirds of its peers sent the same block hash, it commits the new block to its local copy of the blockchain
* a lot direct communication between the nodes - works best in environ with small consensus groups
