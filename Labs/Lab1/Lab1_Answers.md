# Lab 1 Answers

## 2. Fundamental Reasons for Cloud Success

Cloud computing took off because it solves real-world problems for businesses and individuals. One key reason is scalability — companies can adjust resources up or down based on demand without buying new hardware. Another factor is cost efficiency; instead of investing in expensive servers upfront, users pay only for what they use. Accessibility also drives adoption, letting people access data and applications from anywhere with an internet connection.

### Pros
- **Cost savings**: No need for large initial hardware investments
- **Flexibility**: Easily scale resources as needs change
- **Reliability**: Cloud providers offer robust infrastructure with high uptime guarantees

### Cons
- **Security concerns**: Storing data offsite raises risks of breaches
- **Dependency on internet**: Services become unavailable during connectivity issues
- **Potential hidden costs**: Long-term usage or data transfer fees can add up

## 3. Primary Function of a Hypervisor

A hypervisor acts as a middle layer between physical hardware and virtual machines. It manages and allocates physical resources like CPU, memory, and storage to multiple VMs running on the same host. This software enables multiple operating systems to run simultaneously without interfering with each other. It also provides isolation between VMs, ensuring one VM’s issues don’t affect others.

## 4. What is a Virtual Machine (VM)?

A virtual machine is a software-based emulation of a physical computer. It runs its own operating system and applications just like a physical machine, but shares the underlying hardware resources with other VMs through a hypervisor. Think of it as a "computer within a computer" that can be created, modified, or deleted without affecting the host system.

## 5. Benefits of Using Virtual Machines

Virtual machines offer several advantages for users and organizations. They let you run multiple operating systems on a single physical machine, which saves space and reduces hardware costs. VMs also provide strong isolation, so if one crashes, others keep running. You can easily create snapshots of VMs to back up or test changes without risking the original system. They simplify software testing too, allowing developers to test applications on different OS environments quickly.

## 6. Use Cases of Virtual Machines

- **Software Development and Testing**: Developers test applications on multiple OS configurations without needing separate physical machines
- **Server Consolidation**: Companies run multiple servers on a single physical machine to reduce hardware costs and energy consumption
- **Disaster Recovery**: Organizations create VM backups that can be quickly restored in case of system failures
- **Educational Environments**: Students practice with different operating systems and software without affecting school computers
- **Legacy Application Support**: Run older software that isn’t compatible with modern operating systems

## 7. Guest Operating System

b) The operating system installed on a virtual machine

## 8. Virtual Machine Isolation

c) Virtual machines run independently and are isolated from each other and the host system

## 9. Benefit of Virtual Machine Portability

c) It allows virtual machines to be moved between different physical machines with compatible hypervisors

## 10. Purpose of Cloning a Virtual Machine

Cloning a virtual machine creates an exact copy of an existing VM. This saves time when you need multiple identical VMs for testing, development, or deployment. Instead of setting up each VM from scratch, you can clone a base VM with all necessary configurations. Cloning also helps maintain consistency across environments, ensuring all VMs have the same software versions and settings. It’s useful for quickly scaling deployments or creating test environments that match production systems.