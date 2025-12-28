1. **Check & enable virtualization**: Verify support via OS tools (Task Manager, `grep -E 'vmx|svm' /proc/cpuinfo`, or System Report). Enable in BIOS if disabled.
2. **Reasons for cloud success**: Scalability, cost efficiency, accessibility. **Pros**: scalability, cost savings, flexibility. **Cons**: internet dependency, security risks, vendor lock-in.
3. **Hypervisor**: Manages and allocates physical resources to virtual machines.
4. **VM**: A software emulation of a physical computer that runs its own OS and applications.
5. **Benefits**: Hardware independence, isolation, cost savings, easier management, faster provisioning.
6. **Use cases**: Development/testing, server consolidation, disaster recovery, sandboxing, running legacy apps.
7. **Guest OS**: **b) The operating system installed on a virtual machine**.
8. **Isolation**: **c) VMs run independently and are isolated from each other and the host**.
9. **Portability benefit**: **c) VMs can be moved between compatible hypervisors**.
10. **Cloning purpose**: Create an exact copy of a VM for quick deployment, backups, or testing.