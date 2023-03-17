# Transactions

![Transactions](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*lxKwZQiHM1DbDLaV9NT1tw.jpeg)

Transactions are a series of database operations. Each transaction is a single unit of the main task. The data integrity is intact in these transactions since all the operations either fail together or succeed together.

Generally, some databases choose to leave out [ACID](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) transactions because of the other required optimizations and theoretically impossible implementations. As we have already discussed before, ACID transactions are supported by a [relational database](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) while [BASE transactions](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Non-relational-Database) are supported by a non-relational. However, there are exceptions where the [relational database](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Relational%20Database) doesn’t support ACID transactions but some of the [non-relational](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Databases/Non-relational-Database) ones do.

## States on the Transactions

![States on the transactions](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*v95lNd2RaHdzeawAAeARQg.jpeg)

Any transaction that happens in the database can be in either of the following states: -

1. **Active** — Initial State of every transaction where they are being executed.

2. **Partially Committed** — When a transaction executes its very last operation.

3. **Committed** — When a transaction finishes all the operations successfully. The effects establish themselves in the database system afterward.

4. **Failed** — When the checks on the database recovery system fail and cannot go further.

5. **Aborted** — When the transaction reaches the failed state, the recovery manager stops all the write operations which bring the database to the original position before the execution started. The henceforth state is now called aborted and moving forward, the transactions can either restart or kill themselves.

6. **Terminated** — When there are no abortions and the transactions come through successfully, the database system becomes consistent, and the transaction is terminated while the new one will soon start.
