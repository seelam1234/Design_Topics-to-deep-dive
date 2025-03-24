# Design_Topics-to-deep-dive
1. Bloom Filters
2. Consistent Hashing
3. Quorum
4. Leader and Follower
5. Write-ahead Log
6. Segmented Log
7. High-Water Mark
8. Lease
9. Heartbeat
10. Gossip Protocol
11. Phi Accrual Failure Detection
12. Split Brain
13. Fencing
14. Checksum
15. Vector Clocks
16. CAP Theorem
17. PACELC Theorem
18. Hinted Handoff
19. Read Repair
20. Merkle Trees
21. When to use which DB, 
22. Which cache is better  and why  memcache, Redis
23. Trie Data structure in depth
24. How to ensure we read right data after write in replica
25. If data is replicated, replication lag could cause inconsistent data between the primary database and the replicas. There are generally two options to solve this:

    Serve both reads and writes from the primary database only. This approach is easy to set up, but the obvious drawback is scalability. Replicas are used to ensure data reliability, but they don’t serve any traffic, which wastes resources.

    Ensure all replicas are always in-sync. We could use consensus algorithms such as Paxos [21] and Raft [22], or use consensus-based distributed databases such as YugabyteDB [23] or CockroachDB [24]. 

26. Designing such a system is out of scope. One of the core challenges when building it is to optimize it for write-heavy workloads.

To achieve that, we can use Log-Structured Merge-Trees (LSM) to structure the index data on disk. Write path is optimized for sequential writes only. This technique is used in Cassandra, BigTable and RocksDB.

27. Pessimistic locking   is not scalable approach
28. In real life, one might use a geospatial database, such as Geohash in Redis or Postgres with PostGIS extension.
29. server-sent events (SSE)
