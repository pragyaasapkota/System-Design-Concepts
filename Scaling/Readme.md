In this section you will learn about some of the important system design concepts and components used in system design. You will understand the importance of each of these concepts and how to use them to design a system. This section will also cover different components such as web servers, app servers, databases etc.

# Scaling


![Caching](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210209202024/System-Design-Horizontal-and-Vertical-Scaling.png)


Large enterprises actually have fairly large amounts of data, sort of contrary to popular belief. With increasing amounts of data the system should also for the most part grow to really manage it effectively in a fairly big way. This process of growing or shrinking of the system to for the most part handle data actually is called scaling, basically further showing how with increasing amounts of data the system should also particularly grow to specifically manage it effectively

           



### Scaling of any system can specifically be achieved by two ways in a subtle way



## Vertical Scaling

Vertical scaling literally means upgrading the hardware/software of the existing system in a basically major way. Adding more power to it pretty much more RAM, CPU’s and HDD, which really is quite significant. But with pretty vertical scaling there actually is always a limit a max beyond which it cannot generally go higher, demonstrating that basically vertical scaling essentially means upgrading the hardware/software of the existing system in a fairly big way.

                                                              OR
                                
You can add more powers to your machine by adding better processors, RAM, or other power increasing adjustments. Vertical scaling can be easily achieved by switching from small to bigger machines but remember that this involves downtime.   


1. This approach is also referred to as the ‘scale-up‘ approach.
2. It doesn’t require any partitioning of data and all the traffic resides on a single node with more capacity.
3. Easy implementation.
4. Less administrative efforts as you need to manage just one system.
5. Application compatibility is maintained.
6. Mostly used in small and mid-sized companies.
7. MySQL and Amazon RDS is a good example of vertical scaling.

### Drawbacks

1. Limited Scaling.
2. Limited potential for improving network I/O or disk I/O.
3. Replacing the server will require downtime in this approach.
4. Greater risk of outages and hardware failures.
5. Finite scope of upgradeability in the future.
6. Implementation cost is expensive.






## Horizontal Scaling

Generally Horizontal scaling definitely means adding pretty multiple additional systems to really improve the performance, which essentially is quite significant. Typically we might use sort of several pretty low end commodity hardware to really save the cost in a really major way

                                                            Or

In horizontal scaling, we share the processing and memory workload across multiple devices. This approach is the best solution for projects which have requirements for high availability or failover. Most organizations choose this approach because it includes increasing I/O concurrency and reducing the load on existing nodes.

                
1. This approach is also referred to as the ‘scale-out’ approach.
2. Horizontal scalability can be achieved with the help of a distributed file system, clustering, and load–balancing.
3. Traffic can be managed effectively.
4. Easier to run fault-tolerance.
5. Easy to upgrade
6. Instant and continuous availability.
7. Easy to size and resize properly to your needs.
8. Implementation cost is less expensive compared to scaling-up
9. Google with its Gmail and YouTube, Yahoo, Facebook, eBay, Amazon, etc. are heavily utilizing horizontal scaling.
10.Cassandra and MongoDB is a good example of horizontal scaling.


### Drawbacks

1. Complicated architectural design
2. High licensing fees
3. High utility costs such (cooling and electricity)
4. The requirement of extra networking equipment such as routers and switches.







![Caching](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210209202449/Scaling-Concept.png)





## These are some differences between them


# Horizontal Scaling                                  # Vertical Scaling

1. Might need load balancers                      1. Load balancer is not necessary
2. Resilient to system failures                   2. Single point of failures
3. Data inconsistency                             3. Data consistency
4. Scales well                                    4. Has hardware limit for scaling

