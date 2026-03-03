Instance Type - different configurations of processor, memory, and networking packages to choose from 

Block Storage - divides data into fixed sized blocks and stores them separately with their own address

    - high performance
    - commonly used to create virtual disk drives for cloud servers
    * the user manages the file system (deciding how to format, organize, and manage it)
      - can use magnetic or solid state (more expensive drives)
    * used for high performance, as a single system, with low latency 

Object Storage - stores objects with metadata and a unique identifier

    - used for large amounts of unstructured data like photos, videos, backups
    - used to maintain files for a website, build large data stores, and let someone else manage it
    * the cloud provider manages everything. you store the data, and receive it
        - less expensive on a per Gig basis 
        * unstructured data on a massive scale that's mostly hands off 

File Storage - comes with a file system built in (folders, files, hierarchy)

    - more managed than block, but user still organizes and manages folder structure 
    * shared access for multiple users 

Cloud Networking - highly virtualied and customizable 

VLAN (Virtual LAN) - used on-premises to separate data so that only certain areas can be accessed

VPC (Virtual Private Cloud) - used in the cloud to do similar segmentation of data 

    - what is used to separate private from public data
    * your own firewalls and security rules

SDN (Software-defined networking) - the concept of a software controller manages and directing all                   hardware within the network infrastructure

    - enables faster/more flexible network management
    - central controller is now the biggest security concern because it controls everything
        * will have backup controllers, so there's not a single point of failure

Cloud Databases - 
  - 1. IaaS (Infrastructure as a Service)-provider gives the raw infrastructure (VM, storage, network)
           * client manages everything above that (OS, database, apps, data
  - 2. PaaS (Platform as a Service) - provider gives a platform to build and deploy apps on
           * client only manages application and data
  - 3. SaaS (Software as a Service) - provider gives a fully finished app
           - ex: gmail, slaesforce, dropbox, microsoft 365

SECaas (Security as a Service) - simple security functions delivered by a cloud service   
     - CASB (Cloud Access Security Broker) - visibility and control over what cloud service employees are                 using    
         - sees all cloud app usage, blocks unauthorized cloud serviecs, prevents sentitive data upload  
     - IDaas (Identity as a Service) - manages and verifies identity when accessing apps and services  

Cloud Orchestration - the automated coordination and management of multiple cloud services and resources             working together  
      - automatically provisioning, configuring, scaling, and managing cloud infrastructure

Application Programming Interfaces (API's) 
        - is a standardized communication bridge that allows two apps to talk to each other   
        - it carries the request to one app, and brings back the response as well  
    * within cloud orchestration, API calls are made automatically based on rules & conditions  
        - when traffic spikes, the system can automatically make API calls to:  
            - spin up new servers, configure load balancer, update firewall rules, notify monitor system

Infrastructure as Code 
        - the idea that admins should never build or manage resources using the command                                   line or graphical interfaces
    - they should write code that performs those actions for them
    * the idea is to write scripts that perform tasks so that it's reusable, instead of building things           up from scratch each time

Containers - lightweight way to package an entire app virtually
  - a way of packaging an app and everything it needs to run(code, libraries, dependencies, configuration)
  - a VM includes a full OS (very heavy, takes time to start, and uses a lot of resources)
  - a container shares the host OS (faster, minimal resources, etc).
    * can run containers inside a VM for extra security
    * containers are less secure in the sense that if an attacker finds a kernel vulnerability, it could           affect every container simultaneously since they're all using the same host OS
   
SOA (Service-Oriented Architecture) 

        - a design philosophy that embraces the use of discrete services that       may be accessed by                 customers in a blackbox fashion
        * software design approach where an app is built as a collection of separate independent services           that communicate with each other through API's
    - 1) services are logical representations of a repeatable business acivity with a specified outcome
    - 2) self-contained
    - 3) may be composed of other services 
    - 4) blackbox nature 

### More services separate from each other and communicating means more potential entry points
Microservices - fine-grained services that provide very small and discreet functions to other services 
    - modern evolution of SOA (even smaller and more independent)
