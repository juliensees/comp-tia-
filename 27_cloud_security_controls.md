### Cloud Firewalls

- Cloud provider maintains it's own firewall for its overall infrastructure

- Network Security Groups - serve as IaaS firewalls for clients themselves
      - known as a virtual firewall (because it's cloud software and not a firewall from hardware on site)
      - maintained by the client
          - allows or blocks based on source, destination, and port (ip address, port, etc)

- Cloud application security - same as on-premises, but easier to implement
      - TLS (Transport Layer Security) - fully automated management of digital certificates 
      - cryptography/full encryption - just a click of a button with cloud security
      - Application virtualization - VM's, etc are available 
      - Secure Web Gateway - deeper "type of firewall" that inspects the content of web traffic
            - can block malicious websites, inspects traffic for malware, prevents data exfiltration

  ### Defense in depth - the use of overlapping security controls!! One fails, another fills the gap

  - Cloud provider security controls
      - cloud native controls - specifically designed for the provider's environment (ease of use/integrated)
              - creates vendor dependency by only using one security option  
      - third-party solutions - separates security products from other vendors not made by cloud provider
              - can work across multiple cloud platforms
              - more flexible due to portability 
              - usually more expensive and complex

     - Resource Policy - limits cloud service usage by users on your network
           - helps prevent errors, reduce the risk of a malicious insider attack, and is a financial control
       
     - Transit Gateway - creates secure connections between VPC's (virtual private cloud) in the cloud, and             VLANs (virtual local area network) on your local network. like a cloud router that provides                       encrypted connections
             - connects multiple VPC's through a central hub
             - enables centralized security monitoring/control and simplies network connectivity
               * but it's now a single point of failure and a high value target if this fails
   
     - vpc's are network segmentation in the cloud, and vlan's are network segmentation on premises
   
     - VPC's are segmented for isolation and security
           - a hacker is limited if they need to keep breaking into each "section"
           - VPC's can be separated for departments, environments (develop, testing), apps, compliance, etc.

    - Secret Management Tools
            - protects/stores encryption keys and other credentials
            - expensive but effective 
