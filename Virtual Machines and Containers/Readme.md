# Virtual Machines and Containers

![Virtual Machines and Containers](https://miro.medium.com/v2/resize:fit:720/format:webp/1*fXBjlw9qdQwzQejBFsUsfA.jpeg)

## What is a Virtual Machine?

Virtual machines (VMs) are virtual environments that work as a system with all the requirements like CPU, memory, network interface, and storage. They are created on a physical hardware system with software called a hypervisor. It divides the resources and hardware separately, so they are prepared to be used by the machines.

On the system, the virtual machines are isolated from the rest and can be moved among the host servers according to the need. There can be multiple VMs in the same hardware — like a server.

![Virtual Machines](https://miro.medium.com/v2/resize:fit:720/format:webp/1*FtjdEPVZC_eEYvQNJ1B6qA.jpeg)

### Hypervisors

Hypervisors are also known as Virtual Machine Monitor (VMM) and isolate the OS, and the resources in the virtual machines. In addition, the hypervisors let on for creating and managing the VMs. All the resources in the devices such as CPU and memory act as a pool of resources so they can be relocated among the hosts or the new virtual machines (VMs).

### Types of Hypervisors

#### 1. Process Virtual Machines

Also called Bare Metal Hypervisors, process virtual machines operate on the host hardware directly by monitoring and managing the guest OS. We can usually see this hypervisor in business environments.

#### 2. System Virtual Machines

Also called Hosted Hypervisors, system virtual machines run on physical host servers within the OS.

### Why do we need virtual machines?

- Server consolidation
- Performance enhancement
- To try a new OS
- To clone a system to other machines
- To run old and incompatible software
- To develop software for various platforms
- To manage the potential malware safely
- To dismantle your system
- To use the VM Snapshots
- To test a new desktop
- To separate the environment of the resources from the rest of the system
- For easy transfer and migration on a network
- For cost-effectiveness

### Disadvantages of using a virtual machine

- More resources are required.
- High storage is required.
- Video game players may not find it significant.

## Containers

Containers are the software units with the logical packaging mechanism of the codes and dependencies like the runtime versions and libraries. With the help of containers, the application runs quickly and reliably from one computing environment to another. The applications are abstracted from the environment where they run making the deployment easy and consistent regardless of the target environment.

![Containers](https://miro.medium.com/v2/resize:fit:720/format:webp/1*8uTk0ADqO17jq77be2iHLw.jpeg)

### Why do we need containers?

- Containers are flexible.
- The responsibilities are separated — developers can work on application logic and dependencies and operations teams can work on deployment and management.
- Containers can run virtually anywhere making it easy to develop and deploy — better workload portability.
- Applications are isolated since the resources are virtualized.
- Developers don’t need to worry about dependencies and environments.
- The lightweight features let the developers use the computing resources according to the requirement.

### Disadvantages of containers

- They are not right for all kinds of tasks.
- Application isolation is weaker.
- There are limited tools in the containers.
- Containers have the potential for sprawl.

## Virtualization Vs. Containerization

| Virtualization                                                               | Containerization                                                                                                                   |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Virtual Machines are larger.                                                 | Containers are smaller in size.                                                                                                    |
| A single machine can have multiple OS - so they appear as multiple machines. | The application is developed in the same OS under the environment - so the same machine works for multiple different environments. |
| The start-up time is higher than containers.                                 | The start-up time is comparatively less.                                                                                           |
| Virtual machines are slower than containers since they have many resources.  | Containers are faster.                                                                                                             |
| The cost of implementation is very high.                                     | The cost of implementation is lower than the VMs.                                                                                  |
| It works best for IT enterprise businesses.                                  | It works best for software developers and related businesses.                                                                      |
