# System Availability

![System Availability](https://miro.medium.com/max/720/1*5IgzHjxpSReoRlQTViehyQ.jpeg)

A good system is reliable. A consistent system that satisfies users’ needs when in conflict counts as a reliable system. The reliability of the system is ensured by the availability of the system. We can safely say that availability is the resiliency of the system. An available system is that which is robust enough to work through failures over the networks and databases so that the system will stand still. However, the system consists of various parts and each part needs to be available for a good user experience.

## Quantifying Availability

We can quantify the availability of the system by calculating the percentage of time for the availability of the primary functionality and operations of the system at each time. As we know that business-critical system needs near-perfect availability, it’s easy to understand that the systems that work on highly variable demands and loads can face a lower availability when the times are off-peak. Yet, since this depends on the use and nature of the system, even the system with low consistency should also have high availability for a good user experience.

For example, if you have a drive for you to store files, they are generally used to just store and occasionally retrieve the file you wish to use. If the system is always available, we can access it anytime but if not, it is very inconvenient and leads to a bad user experience. This also happens to the e-commerce sites where occasional sale days like 11:11 are organized and when the traffic is flooded on these days, the system will collapse if the high-availability system is not implemented to support the loads. As this would be a commercial system, the revenue will also be lost while the system was down. A single moment can cause the loss of millions.

Apart from money, a bad user experience can lead to a bad reputation as well. Sometimes, there are services like AWS S3 which provide their services to others and in case of unavailability of this kind of service, all the other services like Netflix can collapse as well. Hence, it is safe to say that the uptime of the system is what matters the most if you wish to have an excellent system.

The commercial availability numbers of any system are calculated based on annual availability. This means if you ever experienced downtime of 0.1%, this adds up to a total of 8.77 hours a year. Now we know how important fewer downtimes are. We are in the 21st century where everything is digitalized and everything has been integrated into systems, so it’s very important that we even minimize the downtime from 0.1%. For an ideal standard measure, we see for availability with five nines — 99.99999% which means the error margin is just a little over 5 minutes per year.

## Service Level Agreements/Assurances

Service Level Agreements/Assurances or SLAs are generally offered to make online services competitive and meet the market’s expectations. The SLAs are a set of guaranteed service level metrics. For example, 99.999% is one of the metrics which is offered as a service for premium subscriptions. Some databases and cloud service providers propose a trial period if the customer’s use justifies the expectation for such metrics.

However, upon failing to meet the SLA, the customer receives a right to credits or some form of other compensation since the provider fails to meet the assurance. A good example of this would be Google’s SLA for the Maps API.

We can now say that SLA plays an important role while you design a highly available system.

## Designing HA

We can design a highly available system by reducing the ‘single points of failure. They are those points in the system that can lead to unavailability. Here, we design ‘[redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy)’ in the system which leads to high availability. We make some alternatives to the element that might be critical later.

To understand this more clearly, let’s imagine a system that requires authentication. If there is only one authentication service and back end that somehow fails, your system will collapse with the single point of failure but if there were two or more services, the system would stay. This more service means we have added [redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy).

For this, we need to understand and de-compose the system into parts and map out the ones that might cause single points of failure. We can also know which cannot tolerate such failure and the ones that can. The latter is vital to know since designing HA might be expensive in terms of time, money, and resources.
