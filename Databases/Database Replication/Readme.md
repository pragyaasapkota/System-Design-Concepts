# Database Replication

![Database Replication](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*goeZRRmY3C4_69ZJ4fsMYA.jpeg)

The term database replication means sharing the data to make sure it stays consistent between redundant sources like multiple databases. This helps improve reliability, fault tolerance, and accessibility.

There are two kinds of replication for the database. Let’s look at them individually.

## Master-Slave Replication

In the master-slave replication, you can have a master that gives both read and write operations alongside one or more slaves that replicate write but only gives the read operations. To top it off, each slave can replicate its new slave in a tree-like manner. The system fails if the master fails but you can have the master offline and use the slaves for all the read operations until a new master among the slaves is selected.

### Advantages of master-slave replication

- The entire database has multiple backups.
- We don’t need to disturb the master for the read operation, but we can just use the slave.
- Slaves are flexible — can be made offline and synced back at any time.

### Disadvantages of master-slave replication

- More hardware is required.
- If the master fails, downtime is created, and the loss of data is possible.
- The complexity is increased.
- All the writes are required in the master.
- As the number of slaves increases, the times we must replicate also increases causing replication lag.

![Replication](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*1qBlQxpvmzJqs6HYjr97MA.jpeg)

## Master-Master Replication

Moving on, there is master-master replication where both are the masters with the capacity of operating both read and write operations. In case either of the master fails, another one keeps the operation intact.

### Advantages of master-master replication

- Both masters are accessible.
- Simple and automatic to use.
- Quick Failover
- The write operations are synced along both nodes.

### Disadvantages of master-master replication

- Comparatively hard to configure and deploy.
- Synchronization increases the latency in the system and if it is spared, the consistency is loosed.
- Conflict resolution is required.

## Synchronous and Asynchronous replication

On synchronous replication, data is subsequently saved in the primary and replicated storage so that they are always synchronized. However, asynchronous replication just copies the data later when the primary storage has it. The update process is done in fixed schedules which saves cost as well.
