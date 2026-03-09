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
