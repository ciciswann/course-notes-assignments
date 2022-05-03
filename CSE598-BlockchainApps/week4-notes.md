# Week 4 Notes
### Transactions
- Transfer of rights to certain denominations of bitcoins
- Each denomination has its own lock
- Only certain parameters unlock the lock condition
UTXO model (Unspent Transaction Output Model)-
- Want to think of transactions of more of the right to transfer ownership of a asset, never
belongs to a specific individual
- Output Total must be less than or equal to the input total
- Block explorer
- TransactionID = txid
- Confirmation, depends on
- Most current block means there is 1 confirmation
- If it there are 5 more blocks built upon it then there are 6 confirmations
#### On Block Cyper
- Block hash
- Block Height
- Transaction index
- Size,Vsize – size of the transaction in bytes
- LockTime – Used to figureout when a transaction is valid to put it on the blockchain
- Version
#### Raw MetaData:
- Txid – Serialized or Decoded Sha256 hash of the information within a transaction
- Hash – Hash of the transaction (ssame as the TxID)
- Version – Used for Signialing purposes as a flag or signal, version one is default and means
nothing is signaled
- Size,Vsize – size of the transaction in bytes
- LockTime – Used to figureout when a transaction is valid to put it on the blockchain
#### Vin
- Txid – The specific output that the premisions reside in
- VOut – what number that transaction is in
- ScriptSig – Unlocking Script
o “asm” & “Assembly” 
11
- Sequence – allows more variability on locking our transactions around time
Vout
Value –
N – The output number of the aderess
ScriptPubKey
o Asm
o Hex
o reqSigs
o type
o aderess – Object with aderess of the person who can unlock the script
Hex
Blockhash
Confirmations
Time -
blocktime
#### Scripts
- unlocking parameters placed in inputs of a transaction.
- Inputs are pointers to previous outputs in an unlocking script.
- Outputs are scripts and associated value transfer.
- With necessary rights, concatenation enables execution.
Script language
- Written in a stack-based language named Script
o Stack-based with reverse-polish notation
o “Turning Incomplete.”
o No loops
o Not for general use
* Two main components:
1. Simple data (numbers)
2. Operations (functions)
Script Operators (OP Codes) – ½
- OP_DUP – Duplicates the top stack item
- OP_HASH160 – The top item is hashed twice, first with SHA-256, then with RIPEMD-160
- OP_EQUAL – Returns 1 if the top two items are exactly equal, otherwise 0
- OP_VERIFY – Marks transaction as invalid if top stack value is not true (the top stack value is
removed)
12
- OP_EQUALVERIFY – Same OP_EQUAL but runs OP_VERIFY afterward
- OP_CHECKSIG – The entire transaction’s outputs, inputs, and script (from the most recently
executed OP_CODESEPARATOR to the end) are hashed.
o The signature used by OP_CHECKSIG must be a valid signature for this hash and public
key.
 If valid, 1 is returned.
 Otherwise, 0
- OP_CHECKMULTISIG
1. Pops off top element.
2. Pops off number of signatures defined by top element
3. Pops off next element that denotes how many signatures to verify.
4. Pops off one extra element than defined in 3.
Example: Pay-to-Public-Key-Hash (P2PKH)
- Give rights to somebody who can provide a signature for a specific public key
Output Script (ScriptPubKey):
OP_DUP OP_HASH160 <A Public Key Hash> OP_EQUALVERIFY OP_CHECKSIG
Input Script (scriptSig):
<A Signature> <A Public Key>
Combined:
<A Signature> <A Public Key> OP_DUP OP_HASH160 <A Public Key Hash> OP_EQUALVERIFY
OP_CHECKSIG
Put on to stack left to right, signatures and keys are objects that are just placed on the stack.
- Not all input scripts need a signature
- If ends with 1 on stack then it is TRUE and if it is 0 then it is FALSE
Example: 2-of-3 Multi-Signature
- Third part excrew where as one individual must sign off as well as the escrew service
Output Script (scriptPubKey):
2 <Public Key Dragan> <Public Key Nakul> <Public Key Darren> 3 OP_CHECKMULTISIG
Input Script(scriptSig):
13
0 <Signature Dragan> <Signature Nakul>
- The 0 is placed because there is a bug in the opcode check multisig that when it pops off data it
pops off one extra bit of multidata.
- If it is empty and a opcode hasn’t run then it is thought of as invalid
o More of a consensus rule
Example: Pay-toScript-Hash (P2SH) – standard M of N output script
- Increases the complexity of the output
- Structure shifts large data storage from UTXO
- Moves data directly onto the blockchain
- Allows you to receive funds with burdening the receiver instead of the sender
- WARNING: Since we are only storing a hash of the redeeming script the blockchain cannot
verify accuracy and validity of the script it self
o Because hash functions are one way
o Are checked at the time of spending of the attempted output which can lead to funds
lost forever
 Before invalid scripts were easy to check
Input Script with Non-Hashed Output Script:
0 <Signature Dragan> <Signature Nakul> <Signature Darren> [3 Public Key 1 Public Key 2 Public Key 3
Public Key 4 Public Key 5 Public Key 6 Public Key 7 Public Key 8 Public Key 9 Public Key 10 10
OP_CHECKMULTISIG]
Combined with Output Script
0 <Signature Dragan> <Signature Nakul> <Signature Darren> [3 Public Key 1 Public Key 2 Public Key 3
Public Key 4 Public Key 5 Public Key 6 Public Key 7 Public Key 8 Public Key 9 Public Key 10 10
OP_CHECKMULTISIG] OP_HASH160 <78ce86af9gh86g8asdf98e6a7ef> OP_EQUAL
- The stack checks the hash of the given non hashed version of the output script located in t he
input script with the hashed version located in the output script
Redeem Script
0 <Signature Dragan> <Signature Nakul> <Signature Darren> 3 <Public Key 1> <Public Key 2><Public
Key 3><Public Key 4><Public Key 5><Public Key 6><Public Key 7><Public Key 8><Public Key 9><Public
Key 10> 19 OP_CHECKMULTISIG
- Very similar to a regular multisig transaction
#### Advanced Scripts
- Time Component
- Conditional Clauses
#### Time Locks
nLockTime – Transaction-level setting (a field in the transaction data structure)
- Defines the earliest time that a transaction is valid and can be relayed on the network or added
to the blockchain.
- Transaction level Absolute Locktime
nSequence (Result of BIP68/112/113)
- Gave a new meaning to nSequence creating a relative timelock
- Allows an input to specify the earliest time it can be added to a block based on how long ago the
output being spent by that input was induced in a block
- Depends on time elapsed
OP_CODES – at opcode level so can give us more freedom with how wwe use it and where we use it.
- CheckLockTimeVerify
o Allows transaction outputs (rather than whole transactions) to be encumbered by a
timelock
o When called, causes the script to fail unless the nLockTime on the transaction is equal to
or greater than the time parameter provided to the CLTV opcode
o Ensures the CLTV-based timelock has expired before the transaction may be included in
a valid block.
o Same as n lock time as absolute lock time but it is done on output level instead of the
transaction level.
- CheckSequenceVerify (BIP 68/112/113)– like nSequence but at Opcode
o Provides for relative locktime the same feature CLTV provides for absolute locktime
o Causes the script to fail unless the nSequence on the transaction indicates an equal or
greater amount of relative locktime has passed than the parameter provided to the CSV
opcode.
o Ensures the CSV-based timelock has expired before the transaction may be included in a
valid block.
Conditional Clauses
- IF, ELSE, ENDIF
BIP – 16

#### State Channels
* State Channels – is a state altering mode of communication by which you only have the first and
the last transaction recorded on the blockchain everything that happens in between happens off the
blockchain.
* Why? – The main motivation or this is that very often we have veryt small transaction happening
between two parties and it will take to mayn resources to record thoese transactions and it would stress
the network
- Not feasible to have fees that might be larger than the transaction itself
Unidirectional State Channels
- Means funds are only sent to one party.
- Flow is only happening in one direction
#### Example between Alice and bob
1. Alice signs a multi-signature 2 of 2 transaction to set up payment channel with a 1 bitcoin
output requiring signatures from to spend.
2. Alice creates a refund transaction that sends the full transaction that sends the full payment
back to herself but is time locked for a future date and time.
a. Done before Alice sends the transaction to bob incase the transaction doesn’t go as
intended.
3. Alice sends the Refund transaction to Bob and asks for Bob to sign the transaction.
a. Alice Verifies Bob’s signature
4. Alice sends the initial payment Setting up the Unidirectional payment Channel
#### Intermediary Changes
- Alice will create a new transaction that references the initial transaction, like the refund
transaction but without the timelock
- Alice will send this to bob and bob verify the signature and allot her time to watch.
o Bob can broadcast these to the blockchain at anytime.
o If bob disappears then Alice can broadcast the return
#### Bi-directional
- Funds send between to and from two parties
- Using timelocks to limit in time every transaction that is happening between Alice and Bob
#### Example between Alice and Bob
1. Alice creates a initial 2-of-2 transaction with any signiture and sends it to bob
2. Alice then creates and signs a refund transaction with a timelock of April 29th, to Bob
3. Bob verifies Alice’s singiture and then sends it back to Alice.
4. Alice can now sign the initial trnaction and send it to bob
a. Since she has the refund transaction with both signatures
5. Then Bob will verify Alice’s signature and sign it and broadcast it to the network to setup the bidirectional payment channel.
16
#### Intermediary Changes
- Alice or bob create, signs, and sends a new transaction to the other person.
- Each new intermediary transaction references an earlier date then the previous transactions or
refund transactions
- When ever the transaction is over whoever has the latest transaction can sign and broadcast the
network and close the channel
- If Either becomes unresponsive then either one can broadcast the refund after the specified
timelock
- All intermediary transactinos TimeLocked
- Whenever the part feels that have acompished the initial agreement then they will broadcast it
to the rest of the network which will record the last balance of the two accounts
o Will also automatically broadcast of the tranasactions sent expire.
Limitation
- Required use of TimeLocks
- Restrictions of time-nesting
- If we are establishing that for a lot of micro payments we must remember that this is a
timenested thing, so we must know that the timelock enables enough time for the transaction.
### Wallets
- An application that stores and manages keys
- Possibly the most important application that interacts with a blockchain
- Secure storage and access to private and public keys crucial for signing messages/transactions
- Need a good means to protect the keys
1. Non-determaninistic
- Contains private keys (source of public keys)
- Independently generated at random
- Require frequent backups for every key generated
- Value associated with the keys may become inaccessible
2. Deterministic
- Contain private keys collectively derived from an initial seed
- Can be derived by a simple algorithm such as -> the nth private key = SHA256(seed + n)
- Allow for easy backup and storage of keys
- Industry standard for most end users
#### Benefits:
- Relatively easy to store, only need to store the initial seed
3. Hierarchical
- A subset of deterministic wallets
- Keys are derived from a single seed in a tree structure
- Keys may be derived from parent keys, which can derive their own child keys, which can dderive
grandchildren keys.
- Allow sfor more structure and varied uses within a single wallet applications
- Allows public keys to be generated without the association to the private keys.
Mnemonic Codes/Seeds
- A standard created in BIP 0039
o For initial seed generation
o For human-readable representation of a seed
- Easy-to-remember words that represent a seed
- For seeds used in deterministic wallets
- Mnemonic code length can range from 12 to 24 words (depends on required entropy level)
- Takes a seed and makes a set of words representing that key
BIP 32 and BIP 39
BIP-32 – HD Wallets
Bip-39 – Mnemonic Codes
