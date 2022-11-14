# PACELC Theorem: an ELC extension of CAP

![PACELC Theorem](https://miro.medium.com/max/1100/1*PN523ED7ajU-938qY6up8w.jpeg)

We discussed [CAP theorem](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem) in our previous article [here](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem). Now let’s discuss an extension of the [CAP theorem](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem) — PACELC theorem. The first three letters of PAC are the same in [CAP](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem) — Consistency, Availability, and Partition Tolerance. The rest — ELC stands for Else[E], even if the system runs usually, choose between Latency[L] and Consistency[C] of a replicated system. The theorem looks like we maintained high availability by replication.

The question here is why we need PACELC since the [CAP theorem](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem) works a charm even when there are network partitions. But PACELC is an answer when we raise a question on [CAP theorem](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem) — “What will happen to a distributed system if there are no network partitions?”.

There are the following things that the PACELC theorem states about a system that replicates data.

### 1. If statement

When there is a partition in a distributed system, the tradeoff between availability and consistency is done.

### 2. Else statement

When there is no partition and the system is running normally in a distributed system, the tradeoff between latency and consistency is done.

The examples to choose consistency and giving up availability alongside lower latency [PA/EC] are BigTable and HBase. MongoDB is also one of the examples of PA/EC since it goes for availability when there is a partition but chooses a partition in all the other cases. Likewise, to choose availability over consistency after the partition [PA/EL] are Dynamo and Cassandra. Else, they get on with lower latency.

## Advantages of PACELC over CAP Theorem

- Unlike the CAP theorem, PACELC considers latency and consistency as a tradeoff.

- We can effectively use it to choose and design distribution systems.

- It can get over the major downfalls of the [CAP theorem](https://github.com/aygarp-modsiw/Portfolio/tree/master/System%20Design%20Concepts/CAP%20Theorem).