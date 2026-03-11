- Restricting access to networks:
    - Network Perimeter Security - admins want to keep unwanted users out of the network
      * firewalls with ACL's (access control lists)
    - Physical Network Access - limited to authorized users and devices
 
        - Rule Based - restrict access based upon business logic
        - Role Based - restrict access based upon the identity of an individual
        - Time Based - restrict access based upon business hours
        - Location Based - restrict access based upon physical location
     
- Network Access Control (NAC)  
    - intercepts network traffic coming from unknown devices and verifies user is authorized for comms  
      * NAC technology is used to actually scan employees personal device they're using to make sure:  
          * antivirus is installed  
          * OS is patched and up to date  
          * device is encrypted  
         - uses Zero Trust - always verifies, even if it's an employee... computer could be compromised!!  
        * uses an authentication procol called 802.1x to perform access control tasks  
            - Supplicant - the user (their device or connection software) that wants to connect to network  
            - Authenticator - network device controlling access (switch or WAP)  
            - Authentication Server - usually a RADIUS server that verifies supplicant's credentials  
                  - has other authentication jobs, but one of them is Network Access Control  
      * Role-Based Access - after user is authenticated, decides where to place user on the network  
            - student will be on one VLAN, and professors on a different VLAN  
      * Posture Checking (Health Checking) - NAC technology that verifies devices comply with the org's                       security policy before granting broad access  
                  * antivirus software has current signatures  
                  * device has properly configured firewall  
                  * device contains recent security patches  
                      - IF FAILS, MIGHT BE PLACED IN QUARANTINE NETWORK  
          - Agent-Based - software agent installed on the device that reports security status to NAC  
          - Agentless-Based - uses network scanning and other techniques to scan externally   
          - In-Band Approach - NAC device is involved in making/enforcing access control decisions   
          - Out-of-Band Approach - NAC device makes enforcement decisions, but network switch or WAP or                     other components enforce the decision  

- Router Configuration Security
          - perform basic filtering to reduce load on firewalls
          - they use ACL's (access control lists) that have simple rules to allow/deny packets based on:
              * source IP  
          - Extended ACLs also can block:  
              * destination IP  
              * PROTOCOL (tcp, udp, icmp)  
              * port #
  
                  -- routers are stateless ---- no memory of previous packets!!

- Firewalls are much more efficient at blocking and much more advanced rule & security capabilities

### Routers are usually centrally located in secure rooms, SWITCHES ARE SPREAD THROUGHOUT BUILDINGS!!

### Physical access to a switch grants physical control of that portion of the network

- VLAN Security - using Switch Software to configure "LEAST PRIVILEGE RULE"
    
      - VLAN Pruning - limiting the exposure of VLAN's, by limiting the # of switches where they are                       trunked, especially sensitive VLAN's (pruning the VLAN traffic to only what's necessary)  
      * VLAN Trunk Negotiation -  Switches have the possibility of automatic VLAN trunk negotiation                         called DTP (Dynamic Trunking Protocol)  
           - when 2 switchces connect, they can automatically detect each other & setup trunk port  
          * VLAN Hopping - attacker plugs their device into access port  
                  - sends a DTP negotiation message (pretending to be a switch)  
                  - real switch automatically negotiates a trunk connection with attacker device  
                  - attacker then has a trunk connection, receiving all VLAN traffic  
      * Port Security - works by limiting the MAC addresses that may be used on a particular switch port  
                      - admin would have to intervene to change out a device  
          - Static Mode - the admin manually configures each switch port with the allowable MAC address    
          - Dynamic (Sticky) Mode - the admin enables port security and tells the switch to memorize the               first MAC address that it sees on any given port, and then restrict address to that                           MACaddress  
                  - so no one else can ever plug into that port  
                  - but if a mac address was never used... it's open...  
          - DHCP Snooping - switch level security  
              - allows the switch to inspect DHCP messages to ensure they're properly formatted and only                       coming from authorized DHCP servers   

  ### END USER PORT - ANY ETHERNET CABLE PORT THAT SOMEONE CAN JUST PLUG INTO

- MAINTAINING NETWORK AVAILABILITY
 
  - DENIAL OF SERVICE ATTACKS
  - 
    - SYN Flood - attacker creates thousands of partially open TCP connections to a device by sending SYN                   packets, but never answering the SYN act packet to complete 3-way handshake  
    - MAC Flooding - when attackers send lare numbers of different MAC addresses to a switch, hoping to                   overflow the switch's MAC address table and cause it to forget where devices are, and then flood                   traffic out to every switch port, allowing the attacker to eavesdrop on sensitive comms  
            * FLOOD GUARD - some network devices have this to control the # of open connections  
                  - enabling port security protecets switches against MAC flooding attacks  
    - Routing Loops - occur when there are multiple physical paths between two devices and they mistakenly                   begin routing broadcast traffic in a redundant fashion  
              - this causes the network to fill up, and no space left for legitimate use  (Broadcast Storm)
              * Spanning Tree Protocol (STP) - prevents broadcast storms by implementing loop prevention
                  - uses BDPU Guard (Bridge Protocol Data Units) - protects against attackers spoofing BDPU's

- Network Monitoring

      - Firewall logs are rich with information (all allow/deny info)  
          - can figure out the method used to wage a previous attack and maybe identify perpetrator  
          - firewall log can also determine whether the firewall itself was the source of connectivity issues  
          - admins can analyze logs for anomalous connections that differ from past patterns/activity  
          * Network Flow Data - technology that's similar to full packet capture, but slightly less info and                       much less storage for all of that data [DOESN'T TELL WHAT THE TWO SYSTEMS COMMUNICATED]  
              - source and destination systems  
              - source and destination ports  
              - timestamps  
              - amount of data transferred   
      - SIEM (Security Information and Event Managment) - automate the majority of log analysis tasks   
          - firewalls, network devices, servers, and applications  

  - SNMP (Simple Network Management Protocol) - automates many configuration and management of network devices  
        - Managed Devices - routers, switches, WAP's, firewalls, etc.
        - Network Management System - reaches out to SNMP agents on a periodic basis and requests info
            * network activity, device performance, other metrics
                - to retrieve info: sends a GetRequest, device sends back SNMP response
                - to reconfigure: sends a SNMP SetRequest, agent sends back response if achieved (change SSID)
        - SNMP Agent - software that runs on the managed device & communicates with SNMP service
                - can also send out an SNMP Trap back to management system informing of down link with router

  - Isolating Sensitive Systems
    
        - Network Segmentation - separates systems of differing security levels
            - Air-Gapped Systems - extra sensitive information can physically be isolated on premisis
                * more robust security, by having no connection to other networks
        - Jump Server - allow administrative connections between two security zones
            - an extra security checkpoint with strong authentication
            - admins connect to jump server, and then to the target server they want to manage (never directly)
            * also called Jump Boxes/Jump Hosts

  - Zero Trust Networking  
        * DOES NOT RELY ON NETWORK LOCATION TO DETERMINE AUTHORIZED ACTIVITY, BUT INSTEAD AUTHENTICATION TECH   
    - Identity and Access Management (IAM) - cornerstone of zero trust    
          - generates logs of everything identity related (who, when, where, what accessed, failed login)  
          - this data is fed into SIEM as data source  
      - SIEM can then correlate IAM logs with other data (physically impossible location login - alerts.)  
      - SOAR (Security, Orchestration, Automation, and Response) - takes the action (tells IAM to lock account)                - security team programs responses by SOAR to carry out  
     
      - CASB (Cloud Access Security Brokers) - enforce security policies in the cloud  
            - monitors all cloud app usage and generates logs, who accessed what cloud service, what data was  
               uploaded/downloaded, shadow IT  
                - still use IAM for identification, and then CASB monitors activity within cloud  
                * this is all fed into SIEM  

        - EDR (Endpoint Detection and Response) platforms - remediate endpoint security issues  
              - monitor endpoints for signs of compromise  
                  * endpoints are laptops, desktops, servers  
              * ANTIVIRUS RESPONSE TO KNOWN SIGNATURES, EDR MONITORS EVERYTHING AT ENDPONTS AND DETECTS EVEN  
                  NEW SUSPICIOUS BEHAVIOR FROM UNKNOWN THREATS  
                      - BEHAVIOR BASED, NOT SIGNATURE BASED   
                  - it records everything happening on a device and investigates and responds  
                          - CAN ISOLATE COMPROMISED ENDPOINTS   
        - Geofencing - determines the physical location of a user and then only grants the user access to  
                  resources when they're in an authorized area  
                      * used to block access when an employee is traveling in an untrusted area of the world   
    
    
