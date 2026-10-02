# Scaling

Scaling means **increasing or decreasing system resources** to handle changes in traffic, users, or workload.

There are two basic types:
## 1. Vertical Scaling

**Vertical scaling = Scale Up / Scale Down**

Increase or decrease the resources of **one server**.

```
Before:
    Server
    4 CPU + 8 GB RAM

    ↓ Scale Up

After:
    Server
    16 CPU + 32 GB RAM
```

### Example

A server is getting overloaded, so we upgrade it from:

`4 CPU + 8 GB RAM → 16 CPU + 32 GB RAM`

### Advantages

- Simple to implement
- No need to manage multiple servers
- Existing application usually needs little/no modification

### Disadvantages

- Hardware has a maximum limit
- More expensive at higher capacities
- Single server can become a **single point of failure**
- Usually requires downtime during upgrades

---

## 2. Horizontal Scaling

**Horizontal scaling = Scale Out / Scale In**

Increase or decrease the **number of servers/instances**.

```
		 Load Balancer
			  |
  ┌───────────┼───────────┐
  ↓           ↓           ↓
Server 1    Server 2    Server 3
```

If traffic increases:

```
2 Servers → 5 Servers
```

If traffic decreases:

```
5 Servers → 2 Servers
```

### Advantages

- Can handle very large traffic
- Better availability and fault tolerance
- No single server has to handle everything
- Easy to add/remove servers based on demand

### Disadvantages

- More complex
- Requires load balancing
- Application may need to be designed for distributed systems
- Managing multiple servers increases operational complexity

---

## Vertical vs Horizontal Scaling

|Feature|Vertical Scaling|Horizontal Scaling|
|---|---|---|
|Also called|Scale Up|Scale Out|
|Method|Increase server resources|Add more servers|
|Servers|One/few powerful servers|Multiple servers|
|Complexity|Lower|Higher|
|Maximum limit|Hardware limit|Can scale much further|
|Fault tolerance|Lower|Higher|
|Load Balancer|Usually not required|Usually required|
|Example|8 GB → 32 GB RAM|2 servers → 10 servers|

## Simple Example

Imagine a restaurant:

**Vertical Scaling:**

> Make one restaurant bigger and add more tables.

**Horizontal Scaling:**

> Open more restaurant branches.

### In modern web applications

A common architecture is:

```
	  Users
		↓
  Load Balancer
  /     |     \
 ↓      ↓      ↓
Server  Server  Server
 \      |      /
  ↓     ↓     ↓
	 Database
```

This primarily uses **horizontal scaling** to handle increasing traffic.