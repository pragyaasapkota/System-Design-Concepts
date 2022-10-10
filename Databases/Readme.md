# Databases

It's not uncommon that ought to be asked to design the database. You need to choose the different types of storage solutions ([relational](https://github.com/Pragya2056/system-design-concepts-hacktoberfest2022/tree/master/Databases/Relational%20Database) or non-relational) for different use cases. We are going to discuss some important concepts of databases which are frequently used in system design.

## Database Indexing

Database indexes are a data structure that facilitates the fast searching of databases. They are typically used to look up one or two values in each record. We can use indexing for problems where we need to retrieve a value from a large number of rows in a row.

     Indexing is the way of sorting a number of records on multiple fields. When you add an index in a table on a field, it creates another data structure that holds the field value and pointer to the record it relates to. This index structure is then sorted, allowing binary searches to be performed on it.

## Replication

If your database is overloaded, it will crash at a certain point. To avoid this kind of failure we use replication which simply means duplicating our database. Replication can be synchronous (at the same time as the changes to the main database) or an asynchronous approach.

![Caching](https://media.geeksforgeeks.org/wp-content/uploads/20200824220433/DataBaseReplicationSystemDesign.png)

## Sharding or Data Partitioning

Data replication solves the availability issue but doesn't solve the throughput and latency issues (speed). In those cases, you need to share your database which means 'chunking down' or partitioning your data records. So sharding data breaks your huge database into smaller databases.
There are two ways to partition your database- horizontal and vertical sharding. Vertical sharding means you take each table and put each table into a new machine. You can take some sort of key like a user ID and break the data into pieces and allocate data to different machines.

![Caching](https://media.geeksforgeeks.org/wp-content/uploads/20200824220542/ShardingorDataPartitioningSystemDesignExample.png)
