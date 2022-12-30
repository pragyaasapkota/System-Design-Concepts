# Denormalization

![Denormalization](https://miro.medium.com/max/1100/1*5fwz5T97vS_lem54yosivA.webp)

When we listen to the term denormalization, the first thought that might cross our mind is that it means reversing normalization which is not true. Denormalization is a database optimization process where redundant data is added to one or more tables. This was originally designed to avoid costly joins in the relational database.

Denormalization pursues to improve read performance over some write performance where the redundant copies of data are written in multiple tables. This saves us the expensive joins. When the data becomes distributed with sharding or federation, managing joins across the network becomes very complex. Acquiring the denormalization process can prevent such complex joins.

## Advantages of Denormalization

- Data retrieving is fast
- Writing queries is easier
- The number of tables is reduced
- Convenient to manage

## Disadvantages of Denormalization

- Inserts and updates are expensive
- Database design is more complex
- Data redundancy is increased
- Data inconsistency is more probable
