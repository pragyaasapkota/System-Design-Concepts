# CAP Theorem

CAP is an acronym which stands for Consistency, Availability, and Partition tolerance. The theorem states that any distributed system (collection of computers) can only provide two of these three properties at a time. So no distributed system can have all these three at the same time. The participated system should also manage its data across multiple nodules using virtual machines or physical systems.

You can not achieve all the parcels at the best position in a single database, as there are natural trade- offs between the particulars. You can only pick two out of three at a time and that completely depends on your priorities grounded on your conditions.

For illustration, if your system needs to be available and partition tolerant, then it is impossible to provide consistent data on both the nodes. Traditional relational databases are a natural fit for the CA side whereas Non-relational database machines substantially satisfy AP and CP conditions.

This theorem is also known as **Brewer’s theorem** since it was first proposed by **Eric Brewer**, a computer science professor from U.C. Berkley.

![Screenshot 2022-10-09 090114](https://user-images.githubusercontent.com/69753609/194736528-dabbcee6-d7bc-414f-8c6e-d2fbb4b6798a.png)

* **Consistency** means that when someone queries the system for information, the most up-to-date information is always returned. All the nodes of a distributed system should have consistent data. 

* **Availability** means that if the node is not crashed and user makes a call to the node, then the node can't ignore the request. It must fulfill the operation that the user has requested

* **Partition** tolerance means the if network partition happens within a distributed system, the sytem must continue to operate properly

Take the decision depending on the type of operation and your priorities. Is it really alright if your system goes down for a few seconds or a few minutes, if not then availability should be your foremost concern. If you’re dealing with something with authentic transactional data like a stock transaction or financial transaction you might value consistency above all. Try to choose the technology that is best suited to the trade-offs that you need to fabricate.

# Conclusion

CAP theorem plays a big part in the data management of large and small businesses correspondingly. These systems when mapped out appropriately can alleviate issues such as human inaccuracy to keep data relevant and reduce redundancy.

Likewise, the choice of database structures and management systems permit users to precisely choose the right one based on their requirements. It also understands the data that you are working on and the scalability needed.
