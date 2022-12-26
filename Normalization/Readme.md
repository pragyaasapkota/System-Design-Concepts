# A brief introduction to Normalization

![Normalization](https://miro.medium.com/max/1100/1*fEi55pp-IDPaWiQ-EP_Urg.webp)

Normalization is a process of managing and organizing data in a database. To normalize the data, we create tables and establish relationships between the tables. This helps protect the data and make the database flexible because redundancy and inconsistent dependency are eliminated. A normalized database is structured in a way where you can easily add a new type of data or remove the existing one without changing the original arrangement. The applications that interact with the database also remain unaffected for most time when the database is normalized.

## Normal Forms

Many normal forms act like guidelines that help you get the database normalized. Let’s look at some of them: -

### First Normal Form (1NF)

- Repeating groups are not authorized.
- Each set of related data is identified with a primary key.
- The set of related data should have a separate table.
- A single column can not have mixed data types.

### Second Normal Form (2NF)

- Should satisfy the first normal form
- Partial dependency cannot be tolerated

### Third Normal Form (3NF)

- Should satisfy the second normal form.
- Transitive functional dependencies cannot be tolerated.

### Boyce-Codd Normal Form (BCNF)

The third normal form gets stronger in the BCNF where it addresses certain types of anomalies that were not dealt with in the 3NF. That’s why Boyce-Codd normal form is also known as 3.5 Normal Form (3.5NF).

- Should satisfy the third normal form.
- For every functional dependency X→Y, X should be the super key.

There are more normal forms like 4NF, 5NF, etc. which we will not discuss right now.

If a relational database meets the third normal form, it is normalized because 3NF excludes the insertion, update, and deletion anomalies. However, perfect compliance cannot be accomplished in a real-world system. For example, if we choose to ignore one of the first three rules to normalize, we need to be ready for problems to occur such as redundant data and inconsistent dependencies.

## Advantages of Normalization

- Data Redundancy is reduced

- Database design is better

- Data is more consistent

- Referential integrity is imposed

## Disadvantages of Normalization

- Though the data design is better, it is complex as well

- Performance is slower

- Overhead maintenance

- More joins are required
