# Sharding

## What is Sharding
It refers to a method of distributing and storing data with the same table schema in multiple databases.

<img src="/images/sharding.pngpng" alt="vertical partitioning" width="200">

Before appying Sharding, the drawback of Sharding is to increase programming and operational complexity. Thus, it is necessary to look for other ways to optimize your database.

- Scale-up - use more powerful machine
- Cache
- Consider Read-replicas -> propagation delay(time between propagate the update to the replicas) might cause a serious problem
- Vertically Partition is a way if some colums of a table is being used frequently

  <img src="/images/veritical_partition.png" alt="vertical partitioning" width="400">

  ## Keys
  1. How to read data from distributed databases
  2. How to distribute and store data well in distributed databases?
   
      - It is not well distributed, and when data is concentrated on one side, it naturally becomes a hotspot and the performance slows down.
      - The goal is to distribute evenly

## Sharding Method

### Hash Sharding
<img src="/images/hash-sharding.png" alt="vertical partitioning" width="400">
- Shard key: Determine by hashing database id
  - The size of the Hash will be determined by the number of nodes in the cluster.
- Simple sharding method

**Drawbacks**
- When increasing or decreasing the number of nodes in the cluster,
  - the size of the hash is changed as well as the hash key.
  - Then, all the data distribution rules distributed according to the existing Hash Key will go against each other.
  - Eventually, Re-Sharding is required.
- If the large sized data is stored in the even numbered nodes
  - Since it is distributed by the Hash Key, the efficiency of the space was not considered.


### Dynamic Sharding
<img src="/images/dynamic-sharding.png" alt="vertical partitioning" width="400">

- As the name implies, it can be changed dynamically
- Get Shard Key through Locator Service
- What if increasing the number of nodes in the cluster?
  - All you need to do is add Shard Key to the Locator Service.
  - No changes on the sharding keys of existing data
  - It is a flexible structure for expansion.
  
**Drawbacks**
- Data Relocation
  - Match Shard key Table in Locator Service
- Using Cache or Replication for better performance?
  - Data cannot be found through incorrect routing and an error occurs.
  - There is a disadvantage of having to rely on Locators.