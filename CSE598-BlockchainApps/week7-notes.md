# Week 7 Notes - Peer-to-Peer Networks

### Computer Network Architecture
* Client-server - centralized
* Peer-to-Peer - allows for decentralized network of participants
* Client-Server Network
   * centralized (most common)
   * network hosts (client-server model)
     * server role - provide network resources/services to clients
     * client role - request and consume network resources/services provided by servers
* Peer-to-Peer
   * decentralized
   * network hosts
     * no specific role
     * provide and consume network services - simultaneously functions as a client and server
   * all hosts provide services

### TCP/IP
* blockchain network nodes - connect using TCP/IP 
   * not the only protocols but used as name of entire protocol stack
   * used to share information between nodes
* Transmission Control Protocol/ Internet Protocol
* Routes application specific protocols to the correct application on destination computer
* 4 -layer stack
* uses port numbers - each application runs on computer using separate channel
* Layer 4 - Application - provides applications with standardized data exchange
* Layer 3 - Transport - orders, transmits, confirms packets (TCP)
* Layer 2 - Network - routes packets to specific computer/address (IP)
* Layer 1 - Physical - converts packets into network signals

### Nodes
* What is a blockchain node?
   * a device connected to a blockchain network
     * allows the device to interact with the network
     * allows the device to contribute to the functionality of network 
   * completely voluntary but also completely necessary for deventralized blockchain networks
   * several types with defined roles - focusing on those found in a proof-of-work network
* Types and Roles
   * most structured as peer to peer network at protocol level - influenced by available computational resources
   * others cater to specific subsets of network participants
   * different names and purposes - single role, multiple simultaneous roles
   * routing node - uses routing function(most commonly found function)
   * full node - stores and updates a copy of the full blockchain ledger; only nodes able to independently verify all transactions and blocks
   * wallet node - uses wallet function; stores keys and/or creates and broadcasts transactions
   * mining node - critical for achieving consensus by creating blocks from mining; greatest processing capabilities
* Node Discovery
   * new device must initially discover at least one other node on network
   * DNS seeds - allow new node to find IP address from peers; or node must know IP address of at least one other node
   * establishes TCP connection between nodes - single role; multiple simultaneous roles
   * sends version message with information to test compatibility between nodes
   * version messaging - initial message sent between any two peers; peer will see if versions are compatible
   * compatible peers - node that received version message replies with verack message; connection established
   * newly connected node - 
     * sends addr message with IP address once connected (message is forwarded to neighbors)
     * can send getaddr to peers to ask for the list of IP addresses of other nodes
     * 8-15 peer connections common (network becoming robust)
   * node connections
   * connections can be dropped at any time
     * crucial for nodes to be connected to multiple nodes
     * crucial for nodes to update peer list
     * 8-15 peer connections common and positive indicator
   * most recent connections remembered
     * will default to DNS seeds or provided IP addresses if peers unavailable
     * important to have most up-to-date list of peer nodes IP addresses   
   * peers send messages periodically
     * connection dropped if no communication for period of time 
* Full Node Bootstrap
  * Becoming a full node
    * Construct complete, up-to-date copy of blockchain ledger
      * share current block height
      * peers check if their copy is longer than new node's copy
    * Send getblocks message
      * contains block hash of latest local block
      * displays if new node's block is not the latest in chain
    * send inv message to node that is behind in block
      * contains block hashes of missing blocks in order
    * send getdata messages requesting full block data for blocks the full node lacks     

### Block Propagation
* Blockchain Networks
	* facilitates propagation, or relay, of blocks across nodes
	* decreasing amount of bandwidth & time is a positive outcome - important for scalability
* Block Propagation Topics - traditional block propagation and improved propagation techniques (Compact block and Xthin block)
* 

### SPV Clients
