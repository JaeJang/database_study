# Sharding

## What is Sharding
It refers to a method of distributing and storing data with the same table schema in multiple databases.

Before appying Sharding, the drawback of Sharding is to increase programming and operational complexity. Thus, it is necessary to look for other ways to optimize your database.

- Scale-up - use more powerful machine
- Consider Read-replicas -> propagation delay(time between propagate the update to the replicas) might cause a serious problem
- Vertically Partition is a way if some colums of a table is being used frequently

  <img src="/images/veritical_partition.png" alt="vertical partitioning" width="200">

  ## Keys
  1. How to read data from distributed databases
  2. How to distribute and store data well in distributed databases?
   
      - It is not well distributed, and when data is concentrated on one side, it naturally becomes a hotspot and the performance slows down.
      - The goal is to distribute evenly