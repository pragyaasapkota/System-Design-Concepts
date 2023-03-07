# Service Discovery

![Service Discovery](https://miro.medium.com/v2/resize:fit:720/format:webp/1*BNPztgKyaVTRfwacQT9phQ.jpeg)

Service discovery is a process of detecting services within network [clusters](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Clustering). It works on Service Discovery Protocol (SDP) — a networking standard for detecting network service by identifying resources. Usually, we see services invoke each other via language-level methods or procedure calls in the [monolithic](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Monoliths) application. But modern [microservices](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Microservices) have virtualized or containerized environments where there are instances of a service and their locations that change dynamically. Also, we have mechanisms that enable clients of the service to make requests to the dynamically changing set of temporary service instances.

Some of the common examples of service discovery tools are etcd, Consul, Apache Thrift, Apache Zookeeper, etc.

## Implementations of service discovery

### Client-side Discovery

On the Client-side service discovery, the client looks for the service location of another service by querying a service registry that handles the network locations of all the service instances.

![Client-side Discovery](https://miro.medium.com/v2/resize:fit:720/format:webp/1*DLMgWdTN1Cdy6KCkqXiT0Q.jpeg)

### Server-side Discovery

Likewise, we have an intermediate element like a load balancer where a client requests the service via the load balancer which will be consequently forwarded to the available service in an instant.

![Server-side Discovery](https://miro.medium.com/v2/resize:fit:720/format:webp/1*XO1DePckrEdN59Gc7jWbcA.jpeg)

## What is Service Registry?

Service Registry is a database with the network locations of service instances for the clients to reach out to when required. To note, a service registry is highly available and up to date at any time.

## Service Registration

There are some ways of getting the service information known as service registration.

### Self-Registration

Self-registration registers and de-registers service instances itself in the service registry. It even encourages the service instances to send a [heartbeat request](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Heartbeat%20Messaging) to keep its registration alive.

### Third-Party Registration

Further, we have third-party registration that keeps the track of changes in the running instances by polling the deployment environment or subscribing to events. It also records a new service instance in the database while the service registry also de-registers terminated service instances.

## Service Mesh

When you have [distributed](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Distributed%20System) communication, service-to-service communication is necessary but routing this communication, all the application clusters within and across the system gets complex. Then, comes Service Mesh to the rescue by managing and securing the communications between the individual services. In addition, communication is also made observable. The SDP works on full standards for service detection in the mesh. Some of the common examples of service mesh are [Istio](https://istio.io/latest/about/service-mesh/) and [Envoy](https://www.envoyproxy.io/).
