Hypervisor - the software that creates and manages VM's, allowing one physical machine to run multiple operating systems simultaneously
    - Type 1: Bare Metal Hypervisor - runs directly on the physical hardware, with no underlying OS
            - more efficient/faster
            - used in enterprise and data centers
    - Type 2: Hosted Hypervisor - runs on top of an existing operating system - like an app
            - used for personal/desktop virtualization
    * VM Escape - when malware running inside a VM breaks out of the VM and gains access to the hypervisor or other VMs on the same physical host
    * VM Sprawl - many VMs being created and not properly managed or decommissioned - they become unpatched... security risk

### Compromising a hypervisor gives access to every VM running on that host

VDI (Virtual Desktop Infrastructure - provides network-based access to a desktop computing environment

Application Virtualization (or app streaming) - streams applications to the user's desktop 
    - commonly used to run an old application that maybe only runs on Win XP, when your current machine runs Win 11. (legacy app on a new machine)

    * attack surface reduction, when using sandboxing to contain anything "escaping" and isolating apps from the underlying system 
