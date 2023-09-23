# Consensus Algorithms: Paxos and Raft

![Consensus Algorithms: Paxos and Raft](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*RpPwDw4ugpUljrPXI8ZJXQ.jpeg)

Consensus Algorithms are the foundation of distributed computing systems. It enables multiple nodes to reach an agreement on a shared value or decision. A distributed system expects multiple nodes and processes to cooperate for a common goal, whether it is maintaining a distributed database, replicating data across servers, or electing a leader in a cluster. Hence, consensus helps achieve agreement among the nodes and ensures that they all converge on the same value or decision.

There are two prominent consensus algorithms with widespread recognition in distributed systems:

1. Paxos

2. Raft

Let’s discuss the principles behind Paxos and Raft with their similarities, differences, and real-world applications.

## Paxos: The Pioneer of Consensus

In 1989, Leslie Lamport proposed Paxos as one of the earliest consensus algorithms. It is highly resilient and fault-tolerant for reaching consensus in any distributed system. There are two protocols in Paxos, the Prepare and the Accept.

### 1. Prepare

A node called a proposer broadcasts a proposal to other nodes called acceptors. The latter replies with promises not to accept any proposal with a lower number. So, if a proposal with a higher number is received, the proposal must restart the process again.

### 2. Accept

When the proposer receives promises from a majority of acceptors, an acceptance request is sent. If the majority of acceptors accept the proposal, consensus is reached and the value is chosen.

Paxos is robust and can easily handle network failures, node crashes, and message losses. However, it is challenging to understand and implement correctly, resulting in the development of the Raft consensus algorithm.

## Raft: The Understandable Consensus

To overcome the challenges of Paxos, Diego Ongaro and John Ousterhout introduced Raft in 2013. It was designed with simplicity and understandability in mind so it could address some complexities of Paxos. In addition, it is more accessible to developers.

The core principles of Raft are [leader election](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Leader%20Election), log replication, and safety. The leader node is selected among the participants and it manages the log of commands and replicates it to other nodes. In case of a failure, a new leader is elected.

Some of its key features are leader leases that reduce the risk of split votes and electric churn, and the separation of [leader election](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Leader%20Election) and log replication, which simplifies the algorithm.

## Real-World Applications of Distributed systems

### 1. Distributed Databases

Consensus algorithms are important for distributed databases like Apache Cassandra and etcd, where data consistency is vital.

### 2. Distributed File Systems

Hadoop’s HDFS and Google’s Cloud Spanner use consensus algorithms to manage distributed file storage.

### 3. Container Orchestration

Kubernetes uses etcd with the Raft algorithm to manage cluster state.

### 4. Blockchain

Blockchain networks like Bitcoin and Ethereum use consensus algorithms to ensure agreement on the state of the blockchain ledger.

Consensus algorithms play a crucial role in distributed systems. There are multiple nodes to agree on shared values and decisions to bring reliability and fault tolerance. Paxos and Raft have their areas to shine on — while Paxos is known for its resilience, Raft brings forth simplicity and ease of understanding. These algorithms are really important for engineers and developers working on distributed systems and technologies.
