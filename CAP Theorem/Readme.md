# CAP Theorem

CAP stands for **Consistency, Availability, and Partition tolerance**. The theorem states that a distributed system (collection of computers) should ideally share a single state while performing simultaneously. The shared system should also manage its data across multiple nodes using virtual machines or physical systems.

You 
cannot achieve all the properties at the best level in a single database, as there are natural 
trade-offs between the items. You can only **pick two out of three** at a time and that totally depends 
on your priorities based on your requirements.

For example, if your system needs to be available 
and partition tolerant, then you must be willing to accept some latency in your consistency requirements.
**Traditional relational databases** are a natural fit for the **CA** side whereas **Non-relational database** engines
mostly satisfy **AP and CP** requirements.

This theorem is also known as **Brewer’s theorem** since it was first conveyed by **Eric Brewer**, a computer science professor from U.C. Berkley.

![Screenshot 2022-10-09 090114](https://user-images.githubusercontent.com/69753609/194736528-dabbcee6-d7bc-414f-8c6e-d2fbb4b6798a.png)

* **Consistency** means that any read request will return the most recent write. Data consistency is usually “strong” for SQL databases and for NoSQL databases consistency may be anything from “eventual” to “strong”.

* **Availability** means that a non-responding node must respond in a reasonable amount of time. Not every application needs to run 24/7 with 99.999% availability but most likely you will prefer a database with higher availability.

* **Partition** tolerance means the system will continue to operate despite network or node failures.

Take the decision depending on the type of application and your priorities. Is it actually ok if your system goes down for a few seconds or a few minutes, if not then availability should be your prime concern. If you’re dealing with something with real transactional information like a stock transaction or financial transaction you might value consistency above all. Try to choose the technology that is best suited to the trade-offs that you want to make. 

# Conclusion

CAP theorem plays a big part in the data management of large and small businesses alike. These systems when planned out properly can alleviate issues such as human error to keep data relevant and reduce redundancy.

Furthermore, the choice of database structures and management systems allow users to carefully choose the right one based on their requirements. It also understands the data that you are working on and the scalability required.
