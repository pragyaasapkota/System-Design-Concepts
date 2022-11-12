# Logging, Monitoring, and Alerting

![Logging, Monitoring, and Alerting](https://miro.medium.com/max/1100/1*CH6A911weuVXzUOSWi5_Zw.jpeg)

## Logging

Imagine a system you build five years ago. Now, over time, there must have been a large amount of data in the system among which most is useful. These data give you an idea of the system’s health alongside its problems and performance. In addition, you can have insight into who used your system, how often they used it, what section was most used and what was least used, and so on.

We typically use this data for analytics, performance optimization, and product improvement. As per developers, we use it for debugging purposes. It can help with both console logins during development and bug hunts in the test and production environments.

The most efficient way to keep the data intact is LOGGING — to help in traceability and audits. We need to view the logs as a sequence of consecutive events because the data becomes time-series data and the tools and databases you use should be designed to work with that kind of data.

## Monitoring

After logging is done, the next step is MONITORING. This is the step when you figure out what you do with all the logging data. You need to monitor and analyze the data by developing some tools that can parse through the data and present it in a human-readable way for us to make sense. These data are stored in a database plugged in with other tools build with specific data structures that handle these time-series data.

## Alerting

After you are ensuring active monitoring activities, you need to put up another system that sends you an alert every time there is a significant event in the system. You might have been using this system if you are involved in any kind of stock market. You get notified every time the price goes up or down. As a system designer, you can take advantage of the alert by making the system alert you of errors and failures.

## Conclusion
Logging and monitoring help to keep your data consistent with time so that we can have more benefits. If the data consistency is not maintained, there could be missing fields which might lead to a system error.