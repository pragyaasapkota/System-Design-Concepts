# Relational Database

![Relational Database](https://miro.medium.com/max/1100/1*7G9vdSCtEiddaNyiUbvrRg.jpeg)

A database is a set of data that is structured and held in a computer from where data can be accessed when needed. Two types of databases reside: -

1. Relational Database

2. Non-relational Database

Here, we will discuss the first one — a relational database and soon move to a non-relational database.

A relational Database means a database that administers a relationship between the data you store in the database. The table is structured with zero or more rows alongside one or more columns where the data are represented as entities. It is made sure that each object has the correct data related to it. The relationship is tight and maintains consistency as well.

Let’s see an example: -

A student is an entity with data relating to them like name, student id, gender, faculty, etc.

Let’s see a classic relationship database structure below. This is a highly structured database with the entities upon which the structures are imposed as well.

![Student Database](https://miro.medium.com/max/1100/1*8aiqEm-J51YkfSrewd9X1A.jpeg)

The database has a formalized entity structure called schema which conforms if the data is inserted according to the structure.

Structured Query Language (SQL) is the most common relational database querying language. As the name suggests, SQL interacts with the structured data in the database. That’s the reason why a relational database is called an “SQL database” or “sequel database”. Comparatively, SQL databases handle more complex queries than non-relational databases. Here, the database itself handles these queries. One of the common examples of relational databases is Postgre SQL also known as Postgres.

## ACID Transactions

A relational database follows some features to maintain the data which can be understood as ACID. These features maintain the read and write operations imposed by users to interact with the database. Expanding it, we get,

A=Atomicity

C=Consistent

I=Isolation

D=Durable

Let’s explore them individually,

### Atomicity

The first feature atomicity ensures that if a single transaction includes more than one operation then the entire transaction fails with the failure of any one operation. This means that either the whole transaction is held or none. This helps us identify the failure margin since everything either fails or succeeds — never in between. The entire database remains clean this way.

### Consistency

Moving on, consistency means that each data and transaction in the database is valid. The rules defined in the database remain intact and if the changes are made — they are valid if done under the rules and the rest are invalid. Each transaction done in the database changes its state — every ‘read’ operation receives the most recent ‘write’ operation results.

### Isolation

Further, there is isolation. This allows you to do multiple transactions at the same time, but the database will show it like they have been done serially. They happen concurrently which stays Isolation in ACID because ACCD is neither catchy nor easy to understand.

### Durability

The term durability is associated with a promise that states that once data is stored in a database, it will remain persistent there. The data from all the operations and transactions are stored on disk and not in memory which we discussed earlier in the topic storage.

## Conclusion

The relational database is a structured database that handles more complex data queries in comparison to a non-relational database which we will discuss soon. For now, a concept level of a relational database for a better understanding of system design is better.
