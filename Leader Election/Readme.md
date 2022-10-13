# Leader Election

A distributed system is a network of computers where many servers work together to respond to the client. The main goal of such system is to increase availability and and strong consistency. To achieve this feature more than one servers work concurrently to process same problem. Such system has a problem during updating results as each server solving the problem will update the result which may cause issues in the network.

To avoid such problems in the system we choose a primary server that is responsible to update the final result. The primary server is called a Leader server and the process of appointing the leader is called the Leader Election. Any one of the servers in the network is capable of becoming the leader server.

The servers decide on their own on who the leader might be. There maybe cases where the current leader may be failed due to some problems in such case the servers can conduct a new election to appoint new leader server. The new leader should be accepted by all the servers present in the network. This agreement is called Consensus. 


Consensus is the one value that all the participant agree on. All the other servers rely on the same agreed value. The algorithm to achieve consensus is called Consensus Algorithm. Even when some of the servers are disconnected from others, the concept of blockchain is used to achieve the consensus. This is because consensus is important in a system where multiple independent servers are working on a same task.

 Generally election is handled using a software which has its own leader election architecture. The software stores a key-value pair that ensures both high availability and strong consistency in the system. The software also can determine if the final server in the system is the Leader server or not as it has the identity of a leader server.
 