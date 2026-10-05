
**Database sharding** is a technique where we split a **large database into smaller databases (shards)** and store different data on different servers.

>[!tip] Definition
>Database sharding is a horizontal scaling technique that partitions a large dataset across multiple independent database servers using a shard key, allowing the system to handle larger data and traffic loads.


>- Using an key to partition data is called Horizontal partitioning
>- Vertical partitioning which uses columns


![[Pasted image 20261006003352.png]]

- we can shard the data based on the requirement like tinder for location, or uber.

> [!tip] NOTE
> To connect shards we use joins between tables

## Why do we need Sharding?

A single database server eventually has limitations:

- Storage becomes too large
- Too many read/write requests
- CPU/RAM becomes a bottleneck
- Queries become slower
- Scaling vertically becomes expensive

Sharding allows us to **scale horizontally** by adding more database servers.


# Common Sharding Strategies

### 1. Range-Based Sharding

Data is divided into ranges.

```
Shard 1 → userId 1 - 1,000,000
Shard 2 → userId 1,000,001 - 2,000,000
Shard 3 → userId 2,000,001 - 3,000,000
```

**Problem:** Some shards can become much larger than others.

---

### 2. Hash-Based Sharding

Hash the shard key and use the result to determine the shard.

```
hash(userId) % numberOfShards
```

Example:

```
User 101 → Shard 2
User 102 → Shard 0
User 103 → Shard 1
```

**Advantage:** Usually distributes data more evenly.

---

### 3. Geographic Sharding

Data is divided based on location.

```
India      → Shard 1
USA        → Shard 2
Europe     → Shard 3
Asia       → Shard 4
```

This can also reduce latency because users can access a nearby database.


# what to do when a shard fails

- we can use master slave architecture when there is write request we do it in master
- while slaves  keep polling master for the data and read uses slave
- In case of failure for master slave chooses master among themselves
