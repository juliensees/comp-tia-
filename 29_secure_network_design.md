Security Zones

*Network Border Firewall

- Screened Subnet Zone - (DMZ- Demilitarized Zone) - where public facing servers live  
    - public e-mail servers, web servers, gateways, etc  
    - need to be easily accessible so has a main firewall that everything runs though  

- Intranet - the internal network where most systems reside   
    - can be further divided into more subnetworks if need be  
    - has it's own firewall for DEFENSE IN DEPTH!!   
        - so if an attacker breaks through the first firewall, this is a 2nd security control so they   
            can't access internal servers

- Extranet - intranet segment extended to business partners  
      - selected external access for trusted partners  
      - strict access controls through a VPN  
          * VPN PROVIDES AN ENCRYPTED "TUNNEL" from the outside employee or business partner to inside  
                - this is besides giving IP Masking

- Honeynet - a decoy network designed to attract attackers
       - used to identify potential attackers and study them

- Ad Hoc Network - temporary network that may bypass security controls
          - basically a wireless access point (WAP)

- East-West Traffic - network traffic between systems located within the data center

- North-South Traffic - network traffic between systems in the data center and the internet 

- Zero Trust - security philosophy that you should never trust a user, device, etc if they're inside the 
          network, but instead need to verify it 
          - instead of trusting the location, you trust only after verifying identity
              - MFA, Principle of Least Privilege, Network Segmentation

- VLAN's (Virtual Local Area Network) - a way of logically dividing a physical network into separate                       isolated segments without needing separate physical hardware  
      * each VLAN is it's own separated network with its own IP address  
      - controlled using a hardware network Switch, that is configured using software connected to it  
          * YOU SEPARATE DEPARTMENTS WITH THE SWITCH ACCORDING TO PORTS  

- VLAN Trunking - ports used to connect switches to each other  
        - so port 40 could be the trunk port between finance departments on two different floors (that  
            each have their own network switch)  
              * this is the access point connecting them, and sending the info through a router  

### Switches operate at Layer 2 - move traffic based on MAC addresses within the same network
### Routers operate at Layer 3 - move traffic based on IP addresses between different networks 

* Security device placement

- Network Sensors - device or software that monitor network traffic   
      - Host Based - runs on an individual device and monitors activity only on that machine  
      - Network Based - monitors network traffic through the entire network  
        - IDS (Intrusion Detection System) - monitors & detects, but doesn't block anything  
              - provides additional logging that IPS doesn't provide   
        - IPS (Intrusion Prevention System) - monitors & blocks, but could have false positives  
              - once IDS is fine tuned and knows what's normal and allowed on the system (apps,                           signatures, etc) IPS is usually run fulltime, but still needs updates and fine tuning

  - Port Mirroring
          - the concept of how traffic is copied and sent to an IDS to be scanned (doesnt slow down                     traffic, because it's not stopping the flow of traffic, but analyzing a real-time copy)

  - Security Info and Event Management (SIEM) 
         - uses a network of collectors to gather info and centralize it in one place
         - standardizes different types of log files into one consistent format and analyzes it
         * SIEM then connects dots across multiple data sources to better see if there was an attack

    - Proxy Servers -
          - sits between users and the internet
          - Forward Proxy - sits between internal users and the internet
            * users request web content through the proxy, fetches it and returns it to the user
                -- external website sees the proxy's IP not the user's IP
            * PROXY INSPECTS, BLOCKS UNWANTED THINGS, LOGS, AND CACHES CONTENT, & HIDES MY IDENTITY  
          - Reverse Proxy - sites in front of internal servers  
            * external users think they're talking directly to your web server but really just proxy  

- VPN Concentrators - a dedicated device that manages a large number of simultaneous VPN connections  
        - sits in the DMZ, used in enterprise environments with many remote users

- SSL Accelerator - dedicated hardware that handles SSL/TLS encryption/decryption  
        - used to free web servers from doing this, and freeing up processing power  
        - belongs in the DMZ

- Load Balancer - distributes traffic across multiple servers for performance/availability  
        - mitigates DDoS attacks by spreading traffic across multiple servers  
        - belongs in the DMZ

- DDoS Mitigation Tools  
        - should be as close to the internet connection as possible  
        - ideally purchased from the ISP

Software-Defined Network (SDN) - a technology that separate the control of network traffic from the                   physical hardware, and instead manages it through centralized software  
        - a single point of failure, so a high value target 
        - enables faster/more flexible network management 

    - Control Plane - exists in all devices, but is taken over by SDN
          - responsible for making routing and switching decisions  
    - Data Plane - exist in all devices, and is controlled by the control plane (or controller)  
                - forwards traffic based on instructions from the controller   

- SD-WAN (Software-Defined Wide Area Network)  
     - extends the benefits of SDN to wide-area networks, like multiple office locations  
            - replaces expensive MLPS with cheaper internet connections  
             - built in encryption for traffic between locations 
