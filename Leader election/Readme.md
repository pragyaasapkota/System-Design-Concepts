# Leader Election

Sometimes horizontally scaling a system is as simple as spinning up a cluster of nodes and letting each node respond to whatever subset of the incoming requests they receive. At other times, the task at hand requires more precise coordination between the nodes and it’s helpful to have a **leader** node directing what the **follower** nodes work on.

For example, you want to ensure that only one server is given the responsibility for updating some third party API because multiple updates from different servers could cause issues or run up costs on the third-party's side.

In this case you need to choose that primary server to delegate this update responsibility to.  That process is called leader election.  

A **leader election algorithm** describes how a cluster of nodes without a leader can communicate with each other to choose exactly one of themselves to become the leader. The algorithm is executed whenever the cluster starts or when the leader node goes down.

# When to use

There are three cases to consider when deciding if leader election fits the situation :

* The first case is when each node is roughly the same and there isn't a clear candidate for a permanently assigned leader. This means any node can be elected as leader, and there isn’t a single point of failure required to coordinate the system.

* The second case is when the cluster is doing particularly complex work that needs good coordination. Coordination can mean anything from decisions about how the work is to be divided, to assigning work to specific nodes, or to synthesizing the results of work from different nodes.

* The third case where leader election adds value is when a system executes many distributed writes to data and requires strong consistency. In this situation a leader creates consistency guarantees by being the source of truth on what the most recent state of the system is (and the leader election algorithm must preserve this properly).

# Drawbacks

* The main downside to leader election is complexity: a bad implementation can end up with “split brain” where two leaders try to control at the same time, or no leader is elected and the cluster can’t coordinate.

* A leader is a single node, so it can become a bottleneck or temporary single point of failure. Additionally, if the leader starts making bad decisions (whatever that means in the context of directing work for the service), the followers will just do what they're assigned, possibly derailing the entire cluster.

* The leader / follower model generally makes the best practices of partial deployment and A/B testing harder by requiring the whole cluster to follow the same protocols or be able to respond uniformly to the same leader.

The four most popular leader election algorithms are :

* Bully Algorithm
* Paxos
* RAFT
* Apache ZooKeeper (ZAB)

# Conclusion

Leader election is a strong technique that may be employed in systems to help make them more fault-tolerant and easier to use. However, when we employ leader election, we pay close attention to the guarantees that each protocol gives and, more critically, does not give.
