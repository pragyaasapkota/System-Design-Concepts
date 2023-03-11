# N-Tier Architecture

![N-Tier Architecture](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*c05wnKJU3M3mY43yrs1EPg.jpeg)

The N-Tier Architecture is when the application is divided into logical layers and physical tiers so they are separate and can run on separate machines. Each layer has a specific responsibility and manages dependencies as well. A lower layer can give the services to a higher layer but cannot receive any.

The tiers can either use asynchronous messaging or call each other directly. The layers are available in the tiers which are separated in a way that it’s more [scalable](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling) and resilient. However, the [latency](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Latency%20and%20Throughput) is increased since there are additional network communications in the system.

## Types of N-Tier Architecture

There are two types of layers in N-Tier architecture.

### 1. Closed Layer Architecture

The layer is limited to call the next layer immediately down. It limits the dependencies between the layer despite the unwanted network traffic if the layer can pass the requests along to the next layer.

### 2. Open Layer Architecture

It can call any of the layers that lie below.

_There are three types of tiers in N-Tier Architecture._

### 1. 3-Tier Architecture

There are three different layers in the 3-Tier Architecture.

#### a. Presentation Layer

It handles user interactions with the application.

#### b. Business Logic Layer

Itaccepts data from the layer above and uses business logic to validate it.

#### c. Data Access Layer

It receives the data from the business logic layer and makes the database operations.

### 2. 2-Tier Architecture

In the 2-tier architecture, the presentation layer communicates with the data store and works on the client. Compared to the 3-tier architecture, the 2-tier misses out on the business logic layer. There is no middle layer between the client and the server.

### 3. 1-Tier Architecture

The 1-Tier architecture is also known as single-tier architecture where the application runs as if it was on a personal computer. All the components reside on a single server.

## Merits of N-Tier Architecture

- Layers are sort of a firewall providing extra security
- [Scaling](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling) is easy due to the separate tiers
- Availability is improved
- Maintenance is improved since each tier can be handled by different individuals

## Demerits of N-Tier Architecture

- Network Security is risky
- Network [Latency](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Latency%20and%20Throughput) is increased with the increased number of tiers
- Hardware cost is increased since each tier needs its own
- System complexity is increased as a whole
