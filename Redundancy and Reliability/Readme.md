# Redundancy and Reliability

![Redundancy and Reliability](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*GMuww8w1MAxPRlyshEckWg.jpeg)

Reliability is the ability of a system with consistency and dependability to perform as expected under specific conditions over time. With [redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy), reliability is the probability of not failing in a specific environment for a particular mission time. Since it is a statistical probability and there are absolutely no guarantees, we just try to increase the odds of success rate within reason.

In system design, we commonly use the following probability equation to calculate reliability.

**R(t)=e<sup>-λt</sup>**

In the above equation,

R(t)= Probability of success

t= mission time (a time when the system must execute without an outage)

λ=the constant failure rate overtime (N failures/hour)

1/λ= MTTF (mean time to failure)

We can have an impact on the failure rate (λ) but the environment is handled by the nature of the application. The mission time cannot be generally changed unless we can work on planned maintenance at strategic times. Hence, to have an impact on reliability, we need to work on prudent part selection and design practices.

We can see how redundancy designs improve reliability in a basic math equation. If R is a probability of success and F is a probability of failure, with mathematical set theory, all systems are either successful or failures. However, the sum of these two logical states is unity.

That means:

`R + F = 1`

Nowadays, almost all companies tend to track failures more than successes. This makes the equation calculate reliability by

`R = 1 — F`

If there is a 20% rate of failure,

`R = 1 — 0.2 = 0.80`

The success rate is 80% meaning 80 out of 100 succeed.

To use this concept to calculate reliability, we use the following equation,

`R = 1 — (F1)(F2)`

If there are two redundant systems — 1 and 2 then F1 is the probability of failure of system 1 while F2 is the probability of failure of system 2. If we leverage redundancy, the probability of the given system would be 96% or 96 out of 100 would succeed.

`R = 1 — (0.2)(0.2) = 0.96`

Further, there is another way to calculate reliability where we take the probability equation and instead solve for MTTF (mean time to failure)

**R(t)=e<sup>-λt</sup>=e<sup>-t/MTTF</sup>**

In the above equation,

`MTTF = -(t/ln[R(t)])`

For example, if the system has a mission time of 24 hours a day, 7 days a week, for one year (24/7/365) and you had a success rate of 80%

`MTTF = -(1yr/ln[0.80]) = 4.48`

If we add redundancy, the success rate increases to approximately 96% for the same mission time.

`MTTF = -(1yr/ln[0.96]) = 24.5`

These equations show the improvement in reliability that redundancy can bring to any system or application.

## Levels of Redundancy

Sometimes, it’s better to integrate redundancy to the less reliable components only. Let’s imagine three dependent components with the reliability R1, R2, and R3 respectively. If any one component fails, it brings the entire system down.

![Redundancy levels](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*knneRPLyT2yqHSEJn-vjNA.png)

The reliability of the overall system is calculated by multiplying them together.

`R(system) = (R1)(R2)(R3)`

If R1 = 0.96, R2 = 0.80, and R3 = 0.90,

`System Reliability = (0.96)(0.80)(0.90) = 0.69`

If we apply redundancy to the least reliable component above — R2,

![Redundancy Levels](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*HUsPZU9ZsXkAjG2RWEf6BQ.png)

We have, `R = 1-(F1)(F2)` [Because, `R = 1 — F`]

The original system reliability equation transforms to,

`R(system) = (R1)[1-(F21)(F22)](R3)`

Recalculating with the previous values R1 = 0.96, R2 = 0.80, and R3 = 0.90,

`R(system) = (0.96)[1-(0.10)(0.10)](0.90) = 0.86`

This is a huge improvement by implementing redundancy to only one component. If we add redundancy to all, the system becomes more reliable. We can implement [redundancy](https://github.com/pragyaasapkota/System-Design-Concepts/tree/master/Redundancy) at sensors, cables, power supplies, or any other components.
