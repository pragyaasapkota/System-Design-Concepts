# Redundancy and Availability

![Redundancy and Availability](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*4Ti2UQn4WkK-GSd3G1-7aQ.jpeg)

Availability is the time portion when the system is up and running for a particular mission time. It is usually represented in percentages. For example, 99.99% availability means the system has four nines availability which is a high percentage.

To calculate the availability,

`Availability = Uptime / (Uptime + Downtime)`

To have 100% availability, we need a mission time of 24/7 for six months with no downtime. If we get one day of downtime, the availability decreases to 99.4% automatically. So, if we intend to develop strategies for availability, we must also know and face the fact that we will deal with occasional failures at some point. That’s why we should focus more on providing high availability with reduced downtime and make the repair time as short as possible.

If there is no [redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy), the system downtime depends on,

1. How fast can you detect the failure?

2. How fast can you diagnose the problem?

3. How fast can you repair or replace the failed part of the system?

4. How fast can you make the system back to its full operational status?

Apart from these, in case of hardware failures, we can just replace the bad component or systems instead of trying to repair them. Depending on the accessibility and availability of the replacement, the time of replacement takes minutes up to several days.

In case of a software failure, the system needs to reboot for temporary repair work. But the reboot activity can take seconds to hours depending on the system’s complexity.

Redundancy makes the system downtime depend on the time we take to detect the failure and then switch over to the backup unit. It’s better if we can pull this off within seconds so the system can have sub-millisecond downtimes.

This way, redundancy improves the availability of your system by several orders of magnitude. For example, if there is a system that runs 24/7 for one whole year and has an hour of downtime during the mission, the availability goes down to 99.9% — three nines. Likewise, if the downtime is one second, the availability is 99.99999%, i.e., seven nines.

[Redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy) on a system leads to fast switchovers where the system is not noticeably affected by downtime. Hence, in the practical world, the system doesn’t show the outage by showing 100% availability.
