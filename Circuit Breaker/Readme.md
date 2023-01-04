# Circuit Breaker: A Basic Concept

![Circuit Breaker](https://miro.medium.com/max/720/1*kNojj3PoS6n4smhX3HqJ6A.webp)

A circuit breaker is a design pattern we use in system design that detects failures. It also presents a logic that prevents failure that might occur during maintenance, external system failure, or unexpected problems in the system. The concept is to enclose a protected function call in a circuit breaker which then monitors for possible failures. When the failures reach a certain threshold, the circuit breaker trips which means the remaining calls return with an error without the protected call being made. We can also have monitor alerts in case of the circuit breaker trips in any way.

## Why is a circuit breaker used?

Software systems make remote calls to the software running in different processes that might lie in some other machine across a network in a faraway location. A remote call is more bound to fail and can even hang up without a response until some timeout limit is reached. This is what differentiates remote calls from in-memory calls. If we have numerous incoming calls on an unresponsive supply, you have the chance of running out of critical resources leading to cascading failures across multiple systems.

## Circuit Breaker States

There are three states in circuit breaker which are individually explained below: -

! [Circuit Breaker States](https://miro.medium.com/max/720/1*3uliO6TG3Y8C3OC0C-L0ow.webp)

### 1. Closed

Circuit Breakers are in a closed state when everything is good and normal. The request calls pass through the services normally when circuit breakers are in the closed state. However, when the failures increase and pass the threshold, the circuit breaker trips and moves to our next state — Open.

### 2. Open

Circuit breakers return an error without even invoking the services while in the open state. Eventually, the timeout will be specified with the help of the monitoring system while in the open state and when the certain timeout period elapses, the circuit breaker goes to the half-open state.

### 3. Half-open

The half-open state can go both ways. The circuit breaker can pass a limited number of requests from the service to pass through and invoke the operation. When the requests are successful, the circuit breaker goes to a closed state and when they fail, it goes to the open.
