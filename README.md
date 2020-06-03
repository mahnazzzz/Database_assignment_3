You can find the assignment [Here](https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment3.md)

# Assignment 3


## Sharding:

> Sharding is a method of splitting and storing a single logical dataset in multiple databases. By distributing the data among multiple machines, a cluster of database systems can store larger dataset and handle additional requests. Sharding is necessary if a dataset is too large to be stored in a single database.
When it comes to scaling database, there are challenges, but it is good there is some options. The easiest option, of course, is to scale up your hardware and other choice is sharding or trying to shrink the problem with microservices etc.

 ###  Five sharding approaches

> 1- Sharding by Customer or Tenant:

Multi-tenant applications is that their data model develop gradually over time to provide more and more functionality.  sharding by tenant is a safe (and recommended) approach.  

> 2- Sharding by Geography

Some apps that require data to interact strongly across a defined geographic boundary (eg Foursquare) are less suitable for sharding by geography.

3- Sharding by Entity ID to Randomly Distributed Data

When we send out entity ID, we want to distribute data as straight as possible to maximize parallelism in our system. For a perfectly uniform distribution, you would shard at a random ID, essentially round the robin data.

> 4- Sharding a Graph

like Facebook and Instagram, apps that leverage the social graph. for exemple capture things such as the who (who subscribed to updates, who liked, etc.)

> 5- Sharding by Time Partitioning

An example where time partitioning does make sense is when you're an ad network that only reports 30 days of data.

> The Right Approach to Sharding Depends on Your App
An example where time partitioning does make sense is when you're an ad network that only reports 30 days of data.

## Indexs

> Indexes are used to quickly find data without having to search each row in a database table each time a database table is available. Indexes can be created using one or more columns in a database table that form the basis for both quick random entries and efficient access to ordered records.

## Atomicity

> Atomicity means that multiple operations can be grouped into a single logical device, that is, other threads of control that open the database will either see the changes or none of the changes. Atomicity is important for applications that want to update two related databases (for example, a primary database and secondary index) in a single logical action. Or to an application that wishes to update multiple entries in a database in a single logical action.

## Data Lifecycle Management

> Data modeling decisions should take data lifecycle management into consideration.
The Time to Live or TTL feature in collections expires documents after a period of time. Consider using the TTL feature if your application requires some data to continue in the database for a limited time.


# Modeling

Model | Atomicity |Data Lifecycle Management | Sharding | Indexes
-------|----------|----------- | --------------- |--------------- 
Arrays of Ancestors | X  |  |  | X
Materialized paths | X  |  | X | X
Nested Sets | X |  | X | X
