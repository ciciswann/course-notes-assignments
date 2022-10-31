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
* Lock-based - use locks to lock data items
* Strict two-phase locking (Strict 2PL) Protocol: each transaction must obtain a shared lock on object before reading, and an exclusive lock on object before writing
  * all locks held by a transaction are released when the transaction completes
* Strict2PL allows only serializable schedules - it simplifies transaction aborts
* Lock management - lock and unlock requests are handled by the lock mgr
* locking and unlocking have to be atomic operations
* Shared (read) and exclusive (write) locks
* upgrade - transaction that holds a shared lock can be upgraded to hold and exclusive lock
* Deadlock - cycle of transactions waiting for locks to be released by each other
* two ways of dealing with deadlocks - deadlock prevention and deadlock detection

### Database Recovery
<img width="521" alt="Screen Shot 2022-10-30 at 5 24 24 🌃" src="https://user-images.githubusercontent.com/17733481/198909411-49adf5f3-6ea7-43bd-95c6-b47d2408d568.png">

* Types of failures:
   * transaction failures - transaction aborts (unilaterally or due to deadlock); avg 3% of trans. abort abnormally
   * systems failures - failure of processor, main memory, power supply
   * main memory contents are lost, but secondary storage contents are safe; partial vs. total failure
   * media failures - failure of secondary storage devices such that the stored data is lost; head crash/controller failure
   * communication failures - lost/undeliverable messages; network partitioning  
* recovery manager
* data recovery is the process of restoring data that has accidentally been deleted, corrupted, or is no longer available for any reason
* Local recovery management - volatile storage - main memory (RAM), stable database (secondary storage) resilient 
* <img width="477" alt="Screen Shot 2022-10-30 at 5 30 56 🌃" src="https://user-images.githubusercontent.com/17733481/198909769-b01b252f-657d-4fb8-98d6-dc72cfac0e45.png">
* In-place update recovery information - database log (every action of a transaction must not only perform the action, but must also write a log record to an append-only file (database log)
* <img width="507" alt="Screen Shot 2022-10-30 at 5 33 06 🌃" src="https://user-images.githubusercontent.com/17733481/198909879-6ff701d3-5438-4e81-b7ff-27639915f4d9.png">
* The log - the following actions are recorded in the log:
  * Ti writes an object - old value and new value - must go to disk before the changed page
  * Ti commits/aborts - a log record indicating this action
  * Log records are chained together by Xact id , so that its easy to undo a specific Xact
  * all log related activities are handled transparently by the DBMS
* Logging
  * the log contains information used by the recovery process to restore the consistency of a system. the info may include: transaction identifier, type of operation, items accessed by the trans. to perform the action, old value of item, new value of item
* 3 phases of the Aries recovery algorithm
  * Analysis - scan the log forward (from most recent checkpoint) to identify all Xacts that were actice, and all dirty pages in the buffer pool at the time of the crash
  * Redo - performing an action again; uses the log information and performs the action that might have been done before or not done due to failures; redo operation generates the new image
  * Undo - means to restore the object to its before image; uses the log info and restores the old value of the object
  * write-ahead loggings is used to undo the actions of aboerted transaction and to restore

### Concurrency Control
* Interleaving actions of multiple transactions
* Schedule - an organization of the transactions
* Serial schedule - schedule that does not interleave the actions of different transactions - do T1 first then T2 (no interleaving)
* Equivalent schedule - for any database state the effect of executing the first schedule is identical to the effect of executing the second schedule (S1 and S2 are equivalent when the effect is the same for both)
* Serializable schedule - a schedule that is equivalent to some serial execution of the transactions
* conflict equivalent - two schedules both involve the same actions of the same transactions, every pair of conflicting actios is ordered the same way
* schedule s is conflict serializable if S is conflct equivalent to some serial schedule
* 


