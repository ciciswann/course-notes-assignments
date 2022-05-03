# Week 5

### Introduction to Mining
* How mining works
  * Uses hash functions - SHA256
  * Iteratively hashing block header (change the nonce and hash again)
  * Hash has to be small enough (a low enough number)
  * Valid block submitted to the network
  * Mining protocols (difficulty parameter)
* Exahashes every second

### Attacks
* **51% Attack**
	- Identified by Bitcoin paper; Requires one miner to have more than 50% of the network’s hashing power; would require a lot of energy/financial resources; more theoretical than practical; secretly produce a valid chain that would overrule an existing chain if published; if published and accepted by nodes, can undo/reverse original transactions

* **Selfish Miner Attack**
	- Can be achieved when a miner has one-third or more of the
hash power; requires gaming the network for increased
rewards - e.g. mine a block but delay announcing it to the
network; drives down other miner’s profit; one miner
profiting more than expected may drive other miners off the
network; fewer miners on the network can increase risk of a
51% attack

* **Social Attack**
- Broad class of attacks; targets individual users; website
mimicking an official site;
- Final Note - permissioned blockchains offer more security
(only allow certain actors; don’t rely on proof of work; does
not require the creation of new tokens); 51% attack almost
impossible on a permissioned blockchain

### Mining Pools
- Central commercial server; several miners; pool operator;
continuous revenue for miners
- Advantages: sustainable business model for miners; miners
in pools can benefit from superior performance
- Disadvantages: pool operator controls how hash power is
used; increases risk of 51% Attack
- P2Pools: Node software (currency/application specific); all
contributors paid in a block; not as competitive as
commercial pools
Pros and Cons
- Pros: immutable, when reward declines, energy use
declines
- Cons: high energy use 
