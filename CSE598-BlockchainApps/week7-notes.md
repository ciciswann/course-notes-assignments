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
* Traditional Block Propagation
	* Gossip Protocol
		* Node relays newly heard blocks to 8-10 peers
		* Relayed using a series of messages
	* Process
		* First node validates and advertises block to its peers
			* Uses inventory (inv) message, 64-byte hash of the received block
		* If not heard, sends a getdata message (36 bytes) to first peer
		* In reponse to getdata message, second peer transmits the entire block to the first peer
			* size of a full block (agreed upon by network)
* Compact Block Propagation
	* Introduce in BIP152
		* Design for efficient relay - reduced payload
		* assumes most transactions have already been transmitted to peers - only different information sent
		* collection of 6-byte shortids of transactions the node might not have heard of - include some pre-filled transactions
	* Process
		* All nodes that support compact blocks broadcast
			* sendcmpct(0) for non-expidited
			* sendcmpct(1) for expedited
		* After a new block is mined, the header or inv is sent to receiver node
		* If needed, receiver node sends a getdata(cmpct) request to sender node
		* Sender node responds with a compact block
		* If needed, peer requests all transaction doesn't have in getblocktxn message
		* Response is a blocktxn message that contains full transactions  
* Bloom Filters
	* Data structure that allows probabilistic testing of whether an element is a member of a set
	* false positives are possible
	* false negatives are not possible
	*  peers express the set of transactions in a block and/or mempool
	*  other can check own mempool with bloom filter to determine if they have the same elements
* Xthin Block Propagation
	* Node XTHIN protocol
	* Extreme thin blocks (XTHIN) proposed in BUIP010
	* Payload reduction technique similar to Compact Block - has added complexity to decrease re-transmission rate
	* Process
		* Run NODE XTHIN - lets network know kind of supported block
		* Receiver creates bloom filter
		* Receiver request block getdata
		* Sender sends block - 
			* adds all transaction IDs (8 bytes)
			* Header information
			* Full unknown transactions
		* Receiver reconstructs block using all known and received transactions  

### SPV Clients
* Simplified Payment Verification Clients
* Node with storage restriction
	* not feasible to store full blockchain on some devices (mobile wallets)
	* transaction structure within blocks allows certain clients to verify information - without needing to store large amount of data
* SPVs use merkle trees to structure transactions 
* How SPV clients work
	* downloads only block headers - receives headers from connected full nodes
	* requests and verifies merkle proof of path to transaction
	* problem of not being able to independently verify if other transactions within the block are valid
	* solution is to connect ot multiple nodes - increases probability of not relying on a malicious node
	* risk revealing which rspecific transactions they are interested in
* Randomization in SPV Clients
	* May give up identifying information - could compromise end user's privacy
	* bloom filters address privacy risk 
		* made using information SPV clients are interested in
		* given to the full nodes
		* ask for all information that maps positively to bloom filter
		* SPV Client discards unnecessary information]
		* Note: in a full node sicne all transactions and block are collected, no specific info is given off about that node from the info propagated to it

