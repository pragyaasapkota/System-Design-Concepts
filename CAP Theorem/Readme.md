# CAP Theorem

CAP stands for Consistency, Availability, and Partition tolerance. The theorem states that a distributed system (collection of computers) should immaculately partake a single state while performing contemporaneously. The participated system should also manage its data across multiple nodules using virtual machines or physical systems.

You can not achieve all the parcels at the best position in a single database, as there are natural trade- offs between the particulars. You can only pick two out of three at a time and that completely depends on your priorities grounded on your conditions.

For illustration, if your system needs to be available and partition tolerant, also you must be willing to accept some quiescence in your consistency conditions. Traditional relational databases are a natural fit for the CA side whereas Non-relational database machines substantially satisfy AP and CP conditions.

This theorem is also known as **Brewer’s theorem** since it was first conveyed by **Eric Brewer**, a computer science professor from U.C. Berkley.

![Screenshot 2022-10-09 090114](https://user-images.githubusercontent.com/69753609/194736528-dabbcee6-d7bc-414f-8c6e-d2fbb4b6798a.png)

* **Consistency** means that any read request will return the most recent write. Data consistency is typically “strong” for SQL databases and for NoSQL databases consistency may exist anything from “eventual” to “strong”.

* **Availability** means that a non-responding nodule must respond in a reasonable measure of time. Not every operation needs to run 24/7 with 99.999% availability but most probably you will like a database with higher availability.

* **Partition** tolerance means the system will continue to operate despite network or nodule failures.

Take the decision depending on the type of operation and your priorities. Is it really alright if your system goes down for a few seconds or a few minutes, if not then availability should be your foremost concern. If you’re dealing with something with authentic transactional data like a stock transaction or financial transaction you might value consistency above all. Try to choose the technology that is best suited to the trade-offs that you need to fabricate.

# Conclusion

CAP theorem plays a big part in the data management of large and small businesses correspondingly. These systems when mapped out appropriately can alleviate issues such as human inaccuracy to keep data relevant and reduce redundancy.

Likewise, the choice of database structures and management systems permit users to prcisely choose the right one based on their requirements. It also understands the data that you are working on and the scalability needed.
