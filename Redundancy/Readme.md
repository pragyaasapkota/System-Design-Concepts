# Redundancy

![Redundancy](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*kUC_klEEZYBVQcZMjS_yMw.jpeg)

Redundancy is the most common approach to making reliability and availability better in a system. To accomplish this, we use some extra or duplicate components within a system as a safety measure so that the system can function even in the case of failure and malfunctions. However, adding extra components increases the cost and complexity of the system design. To reduce the system’s complexity, modern electrical and mechanical components on the system give high reliability without redundancy. The problem here is the cost of failure which leads to the use of redundancy again.

There are three models of redundancy.

1. Standby Redundancy

2. N Modular Redundancy

3. 1: N Redundancy

Let’s discuss them individually for a better understanding.

## 1. Standby Redundancy

Also known as backup redundancy, standby redundancy is when you have an identical secondary system to back up your primary system. The secondary system is a spare that exists but doesn’t monitor the system. Both components lie individually and thus should reconcile the input and output signals on the takeover of DUC (Device Under Control). This model gives a “bump” on transfer where the secondary system may send the control signals to DUC that doesn’t sync with the last control signals from the primary system.

Further, we need to place a third-party ‘watchdog’ to monitor the system which will then decide when the switchover will be done. The third-party system will now command the system for the transition to the standby or spare unit and a voter (a component that decides the time to switch over and the unit to give the control of DUC).

The problem with the standby redundancy is that the cost increase in the software development costs of your system will usually be about 2x.

There are two categories of standby redundancy.

### a. Cold Standby Redundancy

In the cold standby redundancy, the secondary spare is powered off to secure reliability. It comes with large downtime than the hot standby since we need to power up the spare and bring it online. The major challenge here is to coordinate synchronization and if it takes longer time to bring the spare online only, there will be a big bump in the switchover.

![Cold Standby](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*EvBmtqrSVGCZd839bYRR1Q.jpeg)

### b. Hot Standby Redundancy

Likewise, in hot standby redundancy, the secondary system is powered up and has the option to monitor the DUC as well. The secondary spare itself acts as a watchdog and/or voter instead of a third party to decide for the switchover. There is no security for the reliability of the standby system as well as the cold standby design. But it reduces the downtime which results in increased availability of the system.

Hot Standby Redundancy is somewhat like Dual Modular Redundancy (DMR). The difference is the tight synchronization between the primary and secondary units. In DMR, both units are in complete synchronization. Some teams refer to all the models as DMR if there are two units.

![Hot Standby](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*iIYwrRJ2fKaIH51gkK9VMQ.jpeg)

## 2. N Modular Redundancy

Moving on, we have N modular redundancy, also known as parallel redundancy. In this model, we run multiple extra or duplicate spares parallelly. All of the involved units are in high synchronization and receive the same input information at the same time. The output values are now compared with each other and the voter will then decide which output value to use. The switchovers are very bumpless in this model.

By comparison, N modular redundancy has faster switchovers than standby which results in high availability because all the units are powered up and engaged with the DUC (Device Under Control). However, this risks the system with common mode failures across all the units. Many techniques avoid the risk but we need to make sure to use the correct one. Sometimes you just need to trust the one and it can be complicated.

If there are two or more units, you have a few of the following approaches under N Modular redundancy.

### a. Dual Modular Redundancy

There are two functional equivalent units in the dual modular redundancy where either one of them can take the control of DUC. The problem arises at the time we need to know to switch over to a secondary spare. But since both are involved to monitor the application, we need to decide what to do in case they disagree. There are few options for us to do in such cases. We can create a vote to break the ties or give control to the secondary unit easily as default assuming it is more trustworthy. For this, you need to run a regular diagnostic on the secondary unit to ensure reliability for a time of need but this is application specific.

If we implement a dual modular redundancy in the system, the average cost nearly doubles while including the cost of additional hardware and extra software development time.

![Dual Modular](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*4sqm8NZCwmCdE5-JT7x8wg.jpeg)

### b. Triple Modular Redundancy

Further, there are three functionally equivalent units in the triple modular redundancy. We can see triple modular redundancy in aerospace applications since the cost of failure is extremely high in them. There are two reasons why triple modular redundancy is more reliable than dual modular.

i. There are two two standby units instead of just one in TMR.

ii. TMR has diversity platforms or diversity programming applied where there are different software or hardware platforms on the redundant systems to prevent common mode failure.

For example, if two units — 1 and 2 are designed using one hardware platform like CompactRIO and the third unit uses PXI or Compact Fieldpoint. This can also be applied to software using LabVIEW for two systems and LabWindows/CVI for the other remaining one.

You can also have different development teams working on separate systems where every system is designed to solve the same problem using the same common requirements. The voter will still decide which team will have the results in the application. The thing with TMR is that it chooses the system to trust based on democracy and the majority. If there are three different answers, the voter decides which system stays or shut down. The switchover is fast and straightforward.

The problem with this approach is that it costs three times more than the cost of the system.

![Triple Modular](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*jYV11bRuX2d94YE7Umb9Zg.jpeg)

### c. Quadruple Modular Redundancy

While the quadruple modular redundancy is fundamentally similar to triple modular, there are four units instead of three which gives more reliability. However, it cost four times more than the system cost and it might be a bit much sometimes.

## 3. 1: N Redundancy

Finally, we have 1: N redundancy where we have a single backup for multiple systems and the backup functions in place of any single one of the active systems. The cost for redundancy is very low with 1: N because there is one single standby spare for numerous primary units. However, this only works when the primary units possess similar functions so that the backup can handle if any one of them fails.

Its disadvantage is that it gets more complex for deciding when to switch on and off a switch matrix that can reroute the signal correctly and efficiently.

![1:N Redundancy](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*4vDe3Mq3k67gp5tRqPU4cw.jpeg)
