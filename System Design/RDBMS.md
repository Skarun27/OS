A relational database like SQL is a collection of data items organized in tables.

**ACID** is a set of properties of relational database [transactions](https://en.wikipedia.org/wiki/Database_transaction).

- **Atomicity** - Each transaction is all or nothing
- **Consistency** - Any transaction will bring the database from one valid state to another
- **Isolation** - Executing transactions concurrently has the same results as if the transactions were executed serially
- **Durability** - Once a transaction has been committed, it will remain so

There are many techniques to scale a relational database: **master-slave replication**, **master-master replication**, **federation**, **sharding**, **denormalization**, and **SQL tuning**.

### 1. Replication in Relational Databases

Replication is a technique used in relational database management systems (RDBMS) to increase the availability, scalability, and fault tolerance of databases. It involves copying and maintaining database objects, like tables, in multiple database instances. Two common replication strategies are Master-Slave (MS) replication and Master-Master (MM) replication.

##### Master-Slave Replication
- **Configuration**: One master database handles both reads and writes, replicating writes to one or more slave databases that handle read-only operations.
- **Failover**: In case of master failure, one of the slaves is promoted to a master, ensuring the continuity of write operations. This process might require additional logic for seamless promotion.
- **Advantages**: Improves read scalability and provides data redundancy for disaster recovery.
- **Disadvantages**:
  - Requires additional logic for slave promotion.
  - Read replicas might experience lag, affecting data freshness.
  - Potential for data loss if the master fails before replicating the writes.

##### Master-Master Replication
- **Configuration**: Two or more master databases can handle reads and writes simultaneously, coordinating with each other to synchronize writes.
- **Failover**: If one master fails, the system continues to operate with the remaining masters handling both reads and writes.
- **Advantages**: Provides high availability and improves write scalability.
- **Disadvantages**:
  - More complex to manage due to the need for conflict resolution and synchronization.
  - May require a load balancer or application-level logic to distribute or route writes.
  - Potential for reduced consistency and increased write latency.

##### Common Disadvantages of Replication
- **Data Loss**: There's a risk of losing data if the master fails before replicating the latest writes to the slaves.
- **Replication Lag**: High write volumes can lead to lag in replicating data to slaves, causing delays in data availability or consistency.
- **Resource Intensive**: Replication can demand additional hardware and complexity, increasing operational costs and management overhead.

##### Summary
Replication in RDBMS, including Master-Slave and Master-Master configurations, aims to enhance database availability, scalability, and disaster recovery capabilities. While each method offers some unique benefits, they also introduce challenges such as the need for conflict resolution, potential data loss, and increased system complexity.

### 2. Federation

Federation (or functional partitioning) splits up databases by function. For example, instead of a single, monolithic database, you could have three databases: **forums**, **users**, and **products**, resulting in less read and write traffic to each database and therefore less replication lag. Smaller databases result in more data that can fit in memory, which in turn results in more cache hits due to improved cache locality. With no single central master serializing writes you can write in parallel, increasing throughput.

##### Disadvantage(s): federation

- Federation is not effective if your schema requires huge functions or tables.
- You'll need to update your application logic to determine which database to read and write.
- Joining data from two databases is more complex with a [server link](http://stackoverflow.com/questions/5145637/querying-data-by-joining-two-tables-in-two-database-on-different-servers).
- Federation adds more hardware and additional complexity.

### 3. Sharding

- **Definition:** Sharding is a database architecture technique for scaling out databases by distributing data across multiple machines or instances.

- **Purpose:** Improves database performance, throughput, and scalability for large databases.

- **How It Works:** Data is partitioned across shards based on a key or algorithm, with each shard potentially hosted on separate hardware or network locations.

- **Advantages:**
  - Enhances performance and scalability.
  - Enables geographical data distribution.
  - Reduces hardware and maintenance costs.

- **Challenges:**
  - Increases management complexity for data consistency.
  - Complicates cross-shard transactions and queries.
  - Requires infrastructure for shard management.

- **Example:** A social media platform stores user data across multiple shards. Each shard handles users from specific geographic regions (e.g., North America, Europe, Asia). When a user logs in, the system directs the request to the appropriate shard based on the user's location, ensuring efficient data retrieval and load distribution.

### 4. Denormalization

- **Definition:** Denormalization involves adding redundancy to a database by combining data from multiple tables into a single table to reduce query complexity.

- **Purpose:** Optimizes read performance by minimizing the need for joins and improving query speed.

- **How It Works:** Involves adding redundant columns, precomputing aggregates, or utilizing materialized views.

- **Advantages:**
  - Improves read operation speed.
  - Simplifies queries.
  - Enhances user experience by reducing response times.

- **Challenges:**
  - Increases storage needs due to redundancy.
  - Complicates update operations.
  - Risk of data inconsistency if not managed properly.

- **Example:** An e-commerce platform's database includes tables for `Orders`, `OrderItems`, `Products`, and `Customers`. To speed up monthly sales reports, product names and prices are added directly to the `OrderItems` table, and customer names and emails to the `Orders` table. This denormalization reduces the need for joining the `Products` and `Customers` tables when generating reports, significantly speeding up the query process.


