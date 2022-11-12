# CAP Theorem: Consistency, Availability, & Partition Tolerance

![CAP Theorem](https://miro.medium.com/max/1100/1*IJSbPVZrMKkDnEBkPjFoDA.jpeg)

CAP Theorem, also known as Brewer Theorem, was first proposed by Eric A. Brewer, a computer science professor from the U.C. Berkley. After two years of Brewer’s proposal, two MIT professors namely Seth Gilbert and Nancy Lynch proved the “Brewer’s Conjecture” which is now known as CAP Theorem.

## What is CAP Theorem?

CAP is an acronym for Consistency, Availability, and Partition Tolerance. The theorem states that any system can have only two of the three properties.

### 1. Consistency

CAP theorem consists of sequential consistency that ensures that every query gets the most-recent data as the response. Every node has updated data in the distributed system to keep it consistent.

**Note:** — Consistency in the CAP theorem is very different from the consistency in [ACID](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Relational%20Database) database transactions. In [ACID](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Relational%20Database), it means the database won’t corrupt when a new transaction is added and in CAP, it means the data is up to date.

### 2. Availability

The second part availability means that each request from the user is returned with the response. This is a guaranteed deal. However, there is no guarantee that the response is the most recent write. Every request for any kind of operation by the user must proceed and send a response.

### 3. Partition Tolerance

Distributed systems are likely to have network partitions occasionally. The third feature partition tolerance tells us that the system runs even when the partition happened. When we implement the feature of partition tolerance, there are two possibilities,

- Cancels the operation and lowers the availability while ensuring consistency.

- Process the operation and have availability but deal with inconsistency.

According to the CAP theorem, only two of the three aforementioned features can be implemented in your distributed system. In addition, the system should include its data in various modules with the help of virtual machines or physical systems for management.

To know what two properties to use on your system, you need to analyze the conditions and use cases of the system. For example, if you decide to make your system available and partition tolerant, you can’t have consistent data.

## CAP Theorem NoSQL database types

[Relational databases](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Relational%20Database) are vertically scalable but [non-relational](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Non-relational-Database) are horizontally scalable. The latter is also distributed in design and can access multiple interconnected nodes by growing on the network. Usually, the [relational database](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Relational%20Database) is the CA fit — Consistent and Available while the non-relational database is AP and CP which are Availability & Partition Tolerance and Consistent & Partition Tolerance respectively. Let’s see all of them individually to have a deeper understanding.

![CA-CP-AP](https://miro.medium.com/max/1100/1*mm6bkV3L7cGNRaM2U9wzTQ.jpeg)

### 1. CP Database

As the topic says, CP stands for Consistency and Partition Tolerance while leaving out availability. If there occurs a partition between two nodes, systems shut down the non-consistent nodes and make them unavailable. This stays until the partition is resolved.

### 2. AP Database

Likewise, AP goes for Availability and Partition Tolerance — getting the consistency off. When a partition occurs, the nodes stay in the same condition but if the nodes are at the wrong end of the partition, there is a possibility that they might have older data. However, they are resynced when the system resolves the partition issues which will automatically take care of the inconsistencies.

### 3. CA Database

Finally, we have Consistency and Availability with the Partition Tolerance out of the picture. In this system, a system can’t work for fault tolerance if there is a partition between two nodes. CA can’t exist outside of theory but [relational database](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Databases/Relational%20Database) like PostgreSQL implements it with multiple nodes using replication.

## MongoDB and CAP theorem (CP)

MongoDB is a NoSQL database management system that stores data as BSON or Binary JSON documents. MongoDB uses CP (Consistency & Partition Tolerance) data store and compromises on availability.

## Conclusion

Every distributed system can choose two from the three properties according to the requirement. If you are okay with your system getting down occasionally, let go of availability and use CP, if not go with either AP or CA. Further, it is crucial that in the system with authentic transactional data related to finance, you need to value Consistency.

However, the CAP theorem raises the question “What will happen to a distributed system if there are no network partitions?” and the answer is given by the [PACELC theorem](https://github.com/Pragya2056/System-Design-Concepts/tree/master/PACELC%20Theorem).