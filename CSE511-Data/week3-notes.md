## Week 3 Notes - Transactions and Recovery

### Transactions/ACID Properties
* In database systems, transactions are user programs that can either read or write data from or to the dbms
* Atomicity, Consistency, Isolation, Durability
* A transaction is the dbms's abstract view of a user program: a sequence of reads and writes
* A user's program may carry out the many operations on the data retrieved, but the DBMS is only concerned about what data is read/written from/to the database
* Concurrency - users submit transactions -> concurrency is achieved by the DBMS which interleaves various transactions -> each transaction must leave the db in a consistent state
  * potential issues - effect of interleaving trans. and crashes
* Database must be in a consistent state at the beginning of a transaction and at the end of the transaction - the db may be temporarily in an inconsistent state during the execution of the transaction
* Atomicity - all or nothing
   * a transaction might commit after completing all its actions, or it could abort after executing some actions
   * all components of trans. run in their entirety or none of them run at all 
   * DBMS logs all actions so that it can undo the actions of aborted transactions
* Consistency - no violation of integrity constraints
   * internal consistency - transactions are correct programs
   * do not violate integrity constraints   
* Isolation - concurrent changes invisible -> serializable
   * serializability - if several transactions are executed concurrently, the results must be the same as if they were executed serially in some order
   * incomplete results - an incomplete transaction cannot reveal its results to other trans. before its commitment 
* Durability - committed updates persist
   * once a transaction commits, the system must guarantee that the results of its operations will never be lost, in spite of subsequent failures
   * database recovery

### Lock-based Concurrency Control and Recovery From Failures
* DBMS are equipped with lock-based protocols to ensure that any transaction to a database cannot read or write data until it acquires an appropriate lock on the transaction. In a big data system where thousands of transactions can be executed simultaneously, it is critical to control the concurrency of transactions.
* 
