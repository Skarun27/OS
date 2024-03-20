
* To maximize write throughput on disk, with consistency:

1. "write back cache" can speed up our writes sometimes - (but inconsistent)
2. Partitioning (fits the use case)
	1. Not only partitioniing helps us store large amt of data, but also speeds up our read
	   and write, by reducing load on every node.
	2. Storing data based on certain range (eg. short urls starting from range a-d, e-h, ...)
	3. Using consistent hashing in place of normal hashing, to promote scaling of partitions
3. Dont use multi leader/leaderless replication - (delayed write/inconsistency).

* Database Replication:
	Types:
	1. Single Leader replication
		1. It is useful to ensure that there are no data conflicts, all writes will go to one node
	2. Multi leader replication
	3. Leaderless replication
		   1. Leaderless and multileader replication is used for increasing write throughput
			beyond just one database node (at the cost of potential write conflicts)
			
* How to handle high write throughout in leaderless replication?
  CRDTs(key-value store) are data structures that allow for concurrent updates by multiple parties across different locations or nodes in a distributed system, and they ensure eventual consistency without the need for central coordination. CRDTs are particularly useful in scenarios where network partitions or intermittent connectivity make constant communication with a central server impractical. They are designed to handle the merging of updates in a way that resolves conflicts deterministically, allowing all replicas of the data to converge to the same state.

* To make in-memory store *fault tolerant*, we can do replication, or maintain write ahead log to make it more durable if not completely. 
* Apply locks on the jobs(in the metadata db) being executed by the consumer, so that other consumer doesn't pick up the same job again.
* **Caching:** Employ caching at various levels (CDN, web servers, application layer) ==to reduce database load== and improve response times.

* Calculations:
  1. 3600 * 24 = 86,400 sec in a day
  2. 