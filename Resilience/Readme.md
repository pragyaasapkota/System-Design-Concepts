# Resilience

![Resilience](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*0OC6sfzR4mWrwIKI9RDhMg.jpeg)

The term resilience means the ability of a system to keep functioning correctly and reliably in case of unexpected events like hardware failures, network outages, or software errors. Resiliency is one of the most important aspects of system design because the software systems need to be capable to handle any kind of unexpected events that might occur during the tenure. They also need to recover quickly from the failures so the operations can continue.

## Fault Tolerant

A resilient system is expected to be fault tolerant which means it can handle all kinds of failures without causing the entire system to fail. To achieve this, we need to use [redundant](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy) hardware and software components, backup systems, and failover mechanisms that help automatically switch to backup systems in case of an emergency i.e., when the primary systems fail.

## Scalability

A resilient system should not just limit itself to being fault tolerant but also should be designed with [scalability](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Scaling) in mind. This means that the system should be able to handle the increased traffic or workload without becoming overloaded or disturbing the performance. For this, we need [load balancing](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Load%20Balancing) and other techniques that help to distribute the workload across multiple systems.

## Failure Recovery

Likewise, a resilient system should be able to recover quickly from failures. The failure detection and the automatic recovery should be very fast without the need for manual intervention. We can do this by using automated monitoring and alerting systems that notify administrators of failures and initiate automated recovery procedures.

## Conclusion

There are numerous ways to make your system resilient but the best way for that would be for the developers to follow established best practices for fault tolerance and scalability. The system should be [redundant](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy) with automated monitoring and alerting mechanisms. The developers should also keep testing and validation tasks regular, so the system resiliency is ensured and the failures have a quick recovery time.
