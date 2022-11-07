## Week 4 Notes - Principles of Distributed and Parallel Database Systems

### Distributed Databases: Why, What?
* Availability, Scalability, Reliability/fault tolerance, transparency
* corporations use distribution in databases - bc distributed databases can avoid large traffic bc the replicated data can be accessed locally
* multiple sites and they're all connected via a communication network
* a collection of multiple, logically interrelated databased distributed over a computer network
* the software that manages the DDB and provides an access mechanism that makes this distribution transparent to the users
* distributed database system: DDBS = DDB + D-DBMS
* Promises - 
   * Transparent mgmt of distributed, fragmented and replicated data
   * Improved reliability/availability thru distributed transactions
   * improved performance - achieve parallelism
   * easier and more economical system expansion
* Transparency = separation of the higher level semantics of a system from the lower level implementation issues; fundamental issue is to provide data independence in the distributed environment

### Data Fragmentation
* fragmentation - db technique to divide a single relation or class of a db into two or more partitions such that the combination of the partitions provides the original db without any loss of information
* this reduces the amount of unnecessary data accessed by the application of the db, thus reducing the number of disk accesses and improving performance time
* Horizontal - place a set of rows into one table and another set of rows into another table
* Vertical - separate attributes (cols) 
* F = {F1, F2}; F1 = σsal<10E; F2 = σsal>20E (σ- selection operator)
* some tuples will be lost - not a good fragmentation
* Desired Properties of Fragmentation:
   * Completeness - decomposition of relation R into fragments R1, R2, ... Rn is complete if and only if each data item in R can also be found in some R
   * Reconstruction - if relation R is decomposed into fragments R1, R2, ... Rn then there should exist some relational operator ∇ such that R = ∇1<=/<=nRi
   * Disjointness - if relation R is decomposed into fragments R1...Rn and data item d is in R then d should not be in any other fragemnt (k =/= j)
* reduces disk space utilization for easy access to data
* Primary Horizontal Fragmentation (PHF) - a horizontal fragment Ri, of relation R consists of all the tuples of R which satisfy a minterm predicate mi
   * given a set of minterm predicates M, there are as many horizontal fragments of relation R as there are minterm predicates
*    <img width="491" alt="Screen Shot 2022-11-06 at 3 03 13 🌃" src="https://user-images.githubusercontent.com/17733481/200200127-e3e0bb84-d624-46eb-ac72-f6c058333d53.png">
* Derived Horizontal Fragmentation (DHF) - you need another attribute from another table
   * given a link L where owner(L)=S and member(L)=R, the derived horizontal fragments of R are defined as Ri = R ⋉F Si, 1≤i≤w
   * where w is the maximum number of fragments that will be defined on R and Si =  σFi(S)
   * where Fi is the formula according to which the primary horizontal fragment Si is defined
* VF: Information requirements - attribute affinities - a measure that indicates how closely related the attributes are; this is obtained from more primitive usage data
   * attribute usage values - given a set of queries Q = {q1,q2...qn} that will run on the relation R[A1, A2,...,An] use(qn8- can be defined accordingly
   *   <img width="539" alt="Screen Shot 2022-11-06 at 3 12 42 🌃" src="https://user-images.githubusercontent.com/17733481/200200536-ddadf83b-707d-4260-a235-148d772d84ad.png">
   * attribute usage matrix
   * the attribute affinity measure between two attributes Ai and Aj of a relation R[A1...An] with respect to the set of applications Q = (q1, q2,...,qq) is defined as:
     * aff(Ai, Aj) = ∑(query access) all queries that access Ai and Aj
     * query access = ∑ access frequency of query * access/execution
* Hybrid Fragmentation - 
   *  <img width="408" alt="Screen Shot 2022-11-06 at 3 15 59 🌃" src="https://user-images.githubusercontent.com/17733481/200200705-a990dd36-7059-4c4f-aae0-5070cf42f952.png">
   *  primary key should be copied to each of the subtables created in vertical frag

### Replication
* Why? - increased availability; faster query evaluation; updates are challenging
* Potentially improved performance = proximity of data to its points of use = requires some support for fragmentation and replication
* Allocation alternatives - non-replicated (partitioned: each fragment resides at only one site); replicated (full replicated: each fragment at each site; partially replicated: each fragment at some of the sites)
* Rule of thumb - if read only queries / update queries >> 1 Replication is advantageous otherwise replication may cause problems
* Fragmentation allocation - optimality - minimal cost, performance; response time and/or throughput - constraints
* Fragmentation Issues - where do queries originate? what is communication cost? what is storage capacity, cost at sites and size of fragments? what is processing power at sites? what is the query processing strategy? do you replicate fragments? what is the cost of updating copies? writes and concurrency control?
* process to perform a single update is slower since it must be updated on different databases to keep the copies consistent

### Intro to Query Processing in a Distributed Database
* <img width="375" alt="Screen Shot 2022-11-06 at 3 31 51 🌃" src="https://user-images.githubusercontent.com/17733481/200201442-ef33208c-105f-4057-b88f-a9fc6afdb72d.png">
* Query processing components - 
   * query language that is used (SQL)
   * query execution methodology ( the steps that one goes through in executing high-level declarative user queries)
   * query optimization - how do we determine the "best" execution plan?
*   <img width="542" alt="Screen Shot 2022-11-06 at 3 36 59 🌃" src="https://user-images.githubusercontent.com/17733481/200201698-747b9734-2c7f-4167-9820-fcac7e44d2d4.png">
* goal is to form a high level query on a distributed database for optimal execution
* <img width="263" alt="Screen Shot 2022-11-06 at 3 44 06 🌃" src="https://user-images.githubusercontent.com/17733481/200201990-96157ad2-2092-4336-8a7b-eacb8b06c4f1.png">
* <img width="518" alt="Screen Shot 2022-11-06 at 3 44 46 🌃" src="https://user-images.githubusercontent.com/17733481/200202019-67fd6ed8-8a24-4eee-af76-b979d31e7edd.png">

### Distributed Query Processing
* <img width="535" alt="Screen Shot 2022-11-06 at 3 46 03 🌃" src="https://user-images.githubusercontent.com/17733481/200202081-7d646175-40eb-4562-830d-10f7c81f4421.png">
* Decomposition - normalization; eliminating redundancy; algebraic rewriting
   * normalization - convert from general language to a standard form (eg relational algebra) 
* Localization - replace relations by corresponding fragments
   * start with query
   * replace relations by fragments
   * push u: up()
   * simplify - eliminate unnecessary operations 
* Optimization 

### Total cost of Query Execution Plan
* <img width="384" alt="Screen Shot 2022-11-06 at 4 23 03 🌃" src="https://user-images.githubusercontent.com/17733481/200203843-cfd5c9cd-3e8e-463b-9f77-36027a979120.png">
* Optimization Statistics - primary cost factor: size of intermediate relations (need to estimate their sizes); make them precise -> more costly to maintain; simplifying assumption: uniform distribution of attribute values in a relation
* query execution plan impacts query performance
* IOs may not be the best metric 
* query separation - separate query into 2 or more steps; optimize each step independently
* 
<img width="473" alt="Screen Shot 2022-11-06 at 5 05 43 🌃" src="https://user-images.githubusercontent.com/17733481/200206629-9231d488-b20a-4a49-9d43-c16022b25c60.png">
* relations have a single attribute
* output has a single attribute

### Introduction to Parallel DBMS
* Pipeline Parallelism - many machines each doing one step in a multi-step proces
* Partition Parallelism - many machines doing the same thing to different pieces of data
* Speed-up - more resources means proportionallly less time for given amount of data
* Scale-up - if resources increased in proportion to increase in data size, (to have the same performance levels when workloads increase)
* Architecture Issues: Shared What? - 
   *  <img width="505" alt="Screen Shot 2022-11-06 at 5 57 46 🌃" src="https://user-images.githubusercontent.com/17733481/200211215-223ee953-c161-47d0-a660-7633d4929f4d.png">
