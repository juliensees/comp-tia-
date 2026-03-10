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
      * VLAN Trunk Negotiation -  Switches have the possibility of automatic VLAN trunk negotiation                       called DTP (Dynamic Trunking Protocol)
           - when 2 switchces connect, they can automatically detect each other & setup trunk port
          * VLAN Hopping - attacker plugs their device into access port
                  - sends a DTP negotiation message (pretending to be a switch)
                  - real switch automatically negotiates a trunk connection with attacker device
                  - attacker then has a trunk connection, receiving all VLAN traffic
      * Port Security - works by limiting the MAC addresses that may be used on a particular switch port
                      - admin would have to intervene to change out a device
          - Static Mode - the admin manually configures each switch port with the allowable MAC address  
          - Dynamic (Sticky) Mode - the admin enables port security and tells the switch to memorize the             first MAC address that it sees on any given port, and then restrict address to that MACaddress
                  - so no one else can ever plug into that port
                  - but if a mac address was never used... it's open...
          - DHCP Snooping - switch level security
              - allows the switch to inspect DHCP messages to ensure they're properly formatted and only                     coming from authorized DHCP servers 

  ### END USER PORT - ANY ETHERNET CABLE PORT THAT SOMEONE CAN JUST PLUG INTO
