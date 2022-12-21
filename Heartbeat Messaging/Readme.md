# Heartbeat Messaging: What is it?

![Heartbeat Messaging](https://miro.medium.com/max/1100/1*BX2L22RJqUpD-V6-ZDbqFg.webp)

In a [distributed system](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System), network failures are bound to happen. Multiple servers are working together in sync which can be disrupted if one of the servers fails in any way. When we discussed [load balancing](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Load%20Balancing) and [leader election](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Leader%20Election), we briefly discussed how the server chooses its leader and how they work periodically with their responsibility. Under leader election, there is a specific server to handle the task of avoiding the clusters from the other servers working on the same problem at once.

We learned the basic concept about it earlier, now we have a term — Heartbeat messaging. It represents those messages that all the servers send the center server at every time interval to let it know that they are functioning well. The heartbeat messaging is a metaphorical representation since the servers tell the central server they are alive.

If there is a case where there is no leader server or the central server, the servers self-select a set of servers and transfer the heartbeat message to those servers. The time interval to send the message is typically set by a few seconds.

This helps the system know if a server is down — it won’t be sending any heartbeat messages for a while.
