---
title: "Cockroach DB"
date: 2019-09-15T21:38:47+01:00
draft: false
weight: 4
---

---

This piece is based on the [white paper for Cockroach DB](https://www.cockroachlabs.com/guides/cockroachdb-the-resilient-geo-distributed-sql-database-sigmod-2020/).

### Fundamentals

Cockroach DB is a scalable, cloud based DBMS targeted towards OLTP systems, particularly ones which are geo-distributed.

**Fault tolerance** is provided by a min. three replica partitioning in each geo-zone. This is similar to how Cassandra (or StorageOS) works in that all data is replicated across the replicas, and the transaction is not considered _committed_ until there is a quorum of agreement that three replicas have the data. The "min" aspect in the paper is interesting as it implies the level of replication is configurable, but not below 3, such that you can always increase resilience in the database, however 3 replicas are required to achieve the fundamental guarantees & there is no option to separate from those guarantees (i.e. to use a small configuration for fast, non-ACID based DBMS storage).

**Geo Distribution** of replicas and partitions is configurable at multiple levels to allow separation of data within geo locations etc. The obvious use case for this is now storing geographically sensitive information relative to the region it should be stored in.

**High Performance** 
