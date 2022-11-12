# Leader Election

![Leader Election](https://miro.medium.com/max/1100/1*c0ZAlvdKLCvqiYbWveGrcQ.jpeg)

We have seen the basic concept of availability [here](https://github.com/Pragya2056/Portfolio/tree/master/System%20Design%20Concepts/System%20Availability) and we know that redundancy leads to high system availability. In the process, we have seen some ways to handle server routing for the incoming requests if the clusters are formed in any way. However, there are cases where you will need a single server to take the lead in a group of servers that are all made for the same tasks. This avoids the issues that might arise if all the servers work concurrently, and each server will update the result individually. This operation is called Leader Election.

Under leader election, we allocate a specific server that handles a particular task to avoid the clusters from other servers working on the same problem at the same time. The lead server takes upon the respective responsibility and then works on that alone. When there are multiple servers, the clusters are formed and they among themselves can decide which will have the lead and which server will take over in case the leader server fails. The new leader is then accepted by all the servers in the network — the agreement is called Consensus. The difficult part to handle under Consensus is to check out if all the servers under the network are in sync with their data and operations along with their states. All the servers are provided with an “agreed-on” value when they need to go through their logic to identify the lead server.

Some software like “etcd” implements the leader concept in their architecture. This is taken as a reference by many developers and engineers for their leader-elected systems. The key-value pairs are stored in similar services and thus the representation of the leader is done.

## Conclusion

Leader election is a very helpful concept when there are multiple servers, and each server needs to be assigned to its respective primary responsibility to prevent the cluster from later in a time of need.