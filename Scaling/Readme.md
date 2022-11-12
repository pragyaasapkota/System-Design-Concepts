# Scaling

![Scaling](https://miro.medium.com/max/1400/1*vJw5-fccbSiztmGj-ZIJSQ.jpeg)

When a system is large, the data in the system is bound to be large. And over time, the data is increased continuously which makes it difficult to manage. With the intention of good data management in the system, the resources are maintained. Let’s see an example of an e-commerce app that sells organic foods only. Earlier, when people were not aware of the benefits of organic foods, the app was rarely used but with time, people began realizing the importance of the food and the app started becoming famous. The app began receiving huge traffic to the point where it feels like it’s losing functionality. The solution to this issue is adding infrastructures in the app so that the functionality increases to handle the load. This is called **Scaling**.

The formal definition of scaling is the ability to add or remove resources to accommodate the increasing or decreasing demand of operations. The point where the requests for the operation in the system reach their limit is known as the scalability limit.

## Types of scaling

There are two types of scaling: -

1. Vertical Scaling

2. Horizontal Scaling

### Vertical Scaling

The first kind of scaling is vertical where we upgrade the existing machine to improve the application capability. This can be done by increasing hardware capacity, i.e., additional CPU, memory, and disc space. The general infrastructure and the design of the app remain the same.

We can also address Vertical Scaling as Scaling up. The most common examples are MySQL and Amazon RDS. It is typically used in small and mid-sized companies.

#### Pros of vertical scaling

1. Simple Implementation process

2. Easier to manage

3. Data consistency

4. No data-partitioning

5. Less administrative effort

6. Lessened software costs

7. Less power consumption

8. Maintained application compatibility.

#### Cons of vertical scaling

1. Replacing or upgrading the server takes time which results in high downtime.

2. Hardware failures and outages are highly possible

3. Future upgradeability has a limited scope.

4. Implementation cost is very expensive.

5. Limited scaling

6. The potential for network I/O or disk I/O is limited.

### Horizontal scaling

Unlike vertical scaling, we add machines to the system instead of upgrading the already existing ones. This helps to distribute the load ([load balancing](https://github.com/Pragya2056/System-Design-Concepts/tree/master/Load%20Balancing)) which ultimately improves the system’s performance. If availability is the highest priority for your system, then horizontal scaling is your go-to add-in. In addition, it has an advantage over vertical scaling on downtime since the load is distributed.

This is also known as the scale-out approach. Load Balancing is very effectively used by increasing I/O concurrency, reducing the load on existing nodes.

#### Pros of horizontal scaling

1. Redundancy increment

2. Better Fault Tolerance

3. Flexible and Efficient

4. Easily Upgradeable

5. More efficient utilization of smaller systems.

6. Enhanced resilience with multiple systems

7. Lower downtime when compared with vertical scaling

#### Cons of horizontal scaling

1. Architectural designs are complicated

2. Data partitioning is required.

3. Big impact on data centers

4. Additional networking pieces of equipment are required. (Switches, Routers, etc.)

5. Utility cost is high (cooling and electricity)

6. Licensing fees are expensive

7. Data inconsistency

8. Downstream services have increased loads.

### Difference between vertical and horizontal scaling

| S.N. | Vertical Scaling | Horizontal Scaling |
| ---- | ---------------- | ------------------ |
| 1. | Load Balancing is not required. | Load Balancing is required. |
| 2. | Single Point of failure. | Resilient to system failure. |
| 3. | Inter-process communication. | Utilizes netowrk calls. |
| 4. | Data Consistency | Data Inconsistency |
| 5. | Hardware Limit | Scales well |
| 6. | Increased downtime | Lest downtime |
| 7. | Data partitioning doesn't happen. | Data partitioning happens. |

### How to choose between Vertical and Horizontal scaling

#### 1. Performance

Horizontal scaling opens your horizon with multiple machines which enhances the performance.

#### 2. Redundancy

Horizontal scaling has built-in redundancy.

#### 3. Flexibility

Horizontal scaling is preferable if you want flexibility in your system.

#### 4. Regularity of upgrades

Since vertical scaling limits your upgrading limits, horizontal is more upgradeable.

#### 5. Geographical distribution

If you want to distribute your data in the system according to geographical location to reduce latency and comply with regulatory standards or to handle disaster recovery scenarios, horizontal scaling is a good option rather than having a single node in vertical scaling.

#### 6. Cost

If your system requirement can be handled in a single node with consistent data, vertical scaling might save you money.

## Conclusion

There might be a debate while choosing between horizontal and vertical scaling and the better idea would be having the option for both. Microservices architectures have more important features to discuss than scalability but if horizontal scalability is added, it can have better capacity elasticity than monolithic architectures.

However, the most efficient advantage will be obtained when both vertical scalability and horizontal scalability are available.