# Week 8 Notes - Governance

### Introduction to Improvement Proposals
* Tool and system or process for decentralized networks
   * adding or changing functionality
   * available on GitHub
   * Vary by network
   * anyone able to submit for consideration
* First was Bitcoin Improvement Proposal
* Reference manual for developers 
   * details backend
   * reference other improvement proposals
   * valuable for implementation and debugging
* Types of Improvement Proposals
   * Consensus rule change
     * every node has to change
     * "Touch" the chain
     * Require more resources
   * Optional implementation
     * nodes choose
     * "Soft" change
     * Require fewer resources

### Decision-Making on Decentralized Networks
* uncertain are the changes to the UTXO
* longer chain wins out - creates orphan block
* Ethereum has uncle block

### Hard and Soft Forks
* block governed by a different protocol than what was started - fork
* soft fork - if the new protocol is backwards compatible with an old protocol
* hard fork - if the new protocol is not as compatible with the old protocol
* any one that doesn't upgrade will get stuck at the block at the hard fork
* everyone has to be on board to have a hard fork
* block could be at least 8 MB - protocol change from 1 MB
* MTP - median time passed

### BIP 9: Activated Hard Forks
* Header of block includes a version
* two version numbers - only difference is you flip a bit
* time start
* round
* time stop

### Dash Governance
* Satoshi protocol allows for governance
* dash adds additional structure
* all nodes are of equal use to the whole network
* what dash proposed is to make master nodes - nodes on the network that are expected to stay online all the time and provided extra services
* master nodes are paid part of the mining reward and cost more to incentivize their existence
* requires 1000 dash - limits possibility of sybil attack
* services - private send and instant send
* private send - node that wants the private send contacts the master node, master node has inputs and makes a transaction that sends to output (don't know which outputs correspond to which inputs) - related to concept of atomic swap
* instant send - higher fee, master node signs that its an instant send changing the consensus rule, if there's a conflicting transaction it's ruled as invalid - Byzantine Fault Tolerance type transaction

