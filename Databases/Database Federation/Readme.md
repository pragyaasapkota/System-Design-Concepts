# Database Federation

![Database Federation](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*kcy3JNaEPqy5VuTWizdXPg.jpeg)

In a database, when it needs to be split up by functions, we use federation architecture. In common words, we can call the federation functional partitioning as well. There are multiple physical databases in the architecture which are presented as a logical database to the end-users. This is because the components here are bound together by federal schemas. The latter has common data throughout the federation that can be used to specify the information to share among the components for a common basis of communication for them. In addition, there are cohesive, unified views of data from multiple data sources in the database federation architecture. There are both structured and unstructured data in the database of these sources.

![Federated database](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*_Ra2kIOpvMaBu3sREmx0BQ.jpeg)

## Why use database federation?

Below is the reason why you should choose database federation.

- Data Sharing is flexible
- Database components have autonomy among themselves
- Heterogenous data can be accessed in a unified way
- Legal databases have loosely coupled applications

## Characteristics of database federation

- The users have no idea where the data is stored. The differences and the implementation of underlying data sources are masked.
- The database system can easily add new sources if required.
- A federated database can have multiple hardware, network protocols, data models, etc.
- The existing database and the interface are not changed.
- The data integration is supported in the federation architecture.

## Are there any demerits?

The database federation also comes with some demerits.

- More hardware is required
- The operations are more complex since joining the data from two databases is hard.
- We are overly dependent on autonomous data sources.
- Query performance
- Scalability
