### Routers, switches, and bridges are the core building blocks of networks around the world

- Switches connect devices to networks  
      - they contain a few, or a few hundred ports  
    * each switch port is connected to one end of a network cable, which runs through conduits in the                 building, and out to devices (like a WAP - Wireless Access Point or wall Ethernet outlet)
    * LIMITED TO CREATING LOCAL NETWORKS ONLY
    * OPERATE AT THE DATA LINK LAYER (LAYER 2 OF OSI MODEL) --- DATA TRANSFERS BETWEEN TWO NODES
          - SOME SWITCHES CAN FUNCTION AT LAYER 3, TO INTERPRET IP ADDRESSES

- Routers
      - connects different networks to each other, making intelligent packet routing decisions ("air                   traffic control")  
      - operates using IP addresses  
      - decides the best path for traffic   
          - can use access control lists (created by the org) to help filter some security access   
    * STATELESS PACKET FILTERING  
            - doesn't have a memory, so it evaluates each packet independently (without remembering  
                what's come before) - Fast, but not as secure  

- Bridges  
      - connects two segments of the same network together  
      - works at Layer 2  
      - operates using MAC addresses  
          - mostly replaced by switches, which have more ports and more intelligence   

- Firewalls
    - usually sit at the network perimeter (BETWEEN ROUTER AND INTERNET)   
      * OFTEN CONNECT 3 NETWORKS TOGETHER  
            - Internet, Internal Network, and Screened Subnet  
        - Screened subnet - accepts direct external connections  
              - isolates those systems (so rest of network can't be attacked easily)  
    * STATEFUL INSPECTIONS - when something tracks open connections  
         - modern firewalls use this (LAYER 4 FIREWALL)  
               - WORKS AT THE TRANSPORT LAYER OF OSI  

      - when a firewall encounters a new connection request, it evalutes it against system admin rules  
         * source system address  
         * destination system address  
         * destination port & protocol  
         * Action (allow or deny)  

      - sometimes serve as NAT gateways  
              - translate between public ip on the internet with private ip on your network  
              - performs content filtering (using URL filtering  

        - WEB APPLICATION FIREWALLS (WAF) - understand how the HTTP protocol works, and look deeper into                 app connections  
              - look for SQL injections, cross-site scripting, buffer overflows, cookie-based attacks   
              - OPERATE AT LAYER 7  
              - sits in front of web servers  
          * Hardware WAF - physical device positioned between network firewall & web server  
          * Software WAF - software runs on the web server to screen requests  
          * Cloud WAF - 3rd party services that remotely filters malicious traffic  
                  - especially good at stopping DDoS attacks (they have extra bandwith to deal with it)

          - XML Firewall - filters acces to XML based services and older APIs
       
### FIREWALLS USE THE DEFAULT DENY OR IMPLICIT DENY RULE - ALWAYS DENY, UNLESS RULE SAYS OTHERWISE

### NGFWs (NEXT-GENERATION FIREWALLS) - LAYER 7 FIREWALLS (work at all levels of the OSI model)  
    * can evaluate a request based on user identity, nature of the app, and time of day  

        - NETWORK BASED FIREWALL - sits on network perimeter    
            - can be open-source, and either software or hardware based  
        - HOST BASED FIREWALL - runs on individual device controlling device's traffic (windows firewall) 
            - almost always proprietary  

- Proxy Servers - used to be an "in-between", of the user and web server.  
      - instead, user connects to the proxy server, and then the web server  
        * more anonymity (web server never learns the network address of the actual user)  
        * proxy servers use caching (better performance/faster)  
        * can perform security tasks  
            - can check users aren't visiting websites containing malicious software  

  - Forward proxy - when the proxy server is on the client's network  
          - client is aware of the proxy server and sends all requests for web content to that server  
                * web server has no idea it's dealing with a proxy  
  - Reverse proxy - they sit on the remote network *work on the server's behalf)  
          - client is not aware they're connected to a remote proxy server  
          - proxy server receives all requests  
  - Transparent proxies (in-line or forced proxies)  
          - work without the client's or server's knowledge  
          - used for content filtering/monitoring   
          - can be used maliciously by attackers, like MITM  

- Load Balancers
        - used to accomodate for large network traffic  
        - distributtes incoming network traffic across multiple servers, so nothing is overwhelmed  
        - provides high availability (no single point of failure) and redundancy  
          * protects against DDoS by distributing traffic  
          * SSL termination - load balancer handles SSL decryption offloading that work from servers  
          * external users only see the load balancer IP and not individual server IP's  

    - Active-Active Mode: two more more load balancers actively handle traffic and actively route info    
    - Active-Passive Mode: one load balancer handles all inbound traffic, while the other monitors those  
            connections.  
                - if the active balancer fails, the passive immediately takes over & routes traffic   
  
    - Layer 4 Load Balancer: makes routing decisions based on network info: IP's and TCP/UDP ports  
    - LAYER 7 Load Balancer: makes routing decisions based on app content: HTTP headers, URL's, cookies  
            * more intelligent -- can route specific requests to specific servers  
  
  - Session Persistence - keeps users connected to the same server throughout their session  
        - implements through cookies, and is necessary for apps that store session data locally  
        * could be an availability concern if the server goes down   

* VPN's - Virtual Private Network  
      * use encryption to create a virtual "tunnel" between two systems over the internet   
            - encrypted on user's end, and then decrypted on the other end (if traffic intercepted, it's                     useless)  
      - VPN's require an endpoint that accepts VPN connections  
                  - orgs with high volumes have a dedicated VPN concentrator   
                  - can use a firewall, router, or server as endpoint but not efficient (slow to process)         - IPsec (Internet Protocol Security) - was used by VPN's to create encrypted tunnels   
            * works at the network layer (Layer 3)  
              - often used for statis site-to-site VPN tunnels   
      * REMOTE USER VPN's often rely on SSL or TLS VPN's that work in APPLICATION LAYER   
                  - work on any system with a web browser and use Port 443 for comms  
                              - 443 is usually allowed through almost every firewall   
      * HTML5 VPN's provide web-based interface that allows users to work with internal network resources             without actually establishing a presence on the internal network  (web server is proxy)
      
      - Site-to-Site VPN's: connect remote offices to each other and headquarters (2 entire networks)    
      - Remote Access VPN's: provide remote access to corporate networks for mobile users (single device) 

      * Full-Tunnel VPN - any traffic leaving the remote device is sent trhough the VPN back to the home                           network and protected by encryption  
      * Split-Tunnel VPN - some traffic is sent through the VPN, while other traffic is sent out through                            the user's local network
                  * reduces burden on VPN's (conserves bandwith), but users sometimes don't realize not                           all their info is encrypted (admins usually have traffic headed to corporate                                       systems through VPN, but not other stuff, but users don't realize this).                                 -- so now not used as much  

- Network Intrusion Detection System (IDS)  
      - sit on the network and monitor traffic, and then alerts administrators   
        * finds:  
              - SQL Injections  
              - malformed Packets  
              - Unusual logins  
              - Botnet Traffic  
            * Because admins are not always available OR TOO MANY ALERTS; IPS TAKES OVER
  
- Intrusion Prevention System (IPS)  
        - CAN TAKE IMMEDIATE/CORRECTIVE ACTION TO BLOCK A THREAT  
        * 1) False Positive Error - when IDS/IPS triggers an alert for an attack that doesn't exist  
        * 2) False Negative Error - when IDS/IPS fails to trigger an alert for an actual attack  

              - Signature Detection Systems  
                    - contain large database with patterns & rules describing past malicious activity  
                          * RULE-BASED DETECTION  
                                - downside is it doesn't alert to new (previously unknown) threats  
                                - but it reduces False-Positive alerts   
              -  Anomaly Detection Systems/Behavior-Based Detection/Heuristic Detection  
                    - builds models of "normal" activity trends , and reports deviations  
                          - a user who normally connects at 8am from chicago is now in asia at 4am  
                          * high false-positive rate  
                                      -  not widely used  
        - IPS Deployment Modes  
                    - Inline(active) deployments  
                          - device sits in the path of network comms and can block suspicious traffic  
                          * can disrupt all network comms because inline IPS is a single point of failure          - Out-of-band (passive) deployments
                    - not on the network path, so doesn't disrupt the flow, but just receives copy of                               traffic  
                    * can still react by sending commands to block future from offending systems, but                                 CANNOT STOP INITIAL ATTACK  
                                - REACTS AFTER ATTACK HAS STARTED

  
