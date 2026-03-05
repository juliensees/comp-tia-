- TCP/IP (Transmission Control Protocol/Internet Protocol) -
  
    - IP is responsible for routing info across networks  
          - provide an IP address  
          - delivers info in packets from source to destination  
          * NETWORK LAYER PROTOCOL  

    - TCP is responsible for the majority of network traffic  
          - establishes connections between two systems before data is transferred   
          - requires the destination system acknowledge receipt of every packet  
                - email and websites like this guaranteed delivery  
          * Transport Layer Protocol!!  
      * Three-way Handshake  
            - SYN flag: opens a connection  
            - ACK flag: used to acknkowledge a SYN or FIN request (receipt of initial flag), and also
                an acknowledgement/expectation of what sequence # it's expecting back next time.  
            - FIN flag: closes a connection
        
        *3-way handshake is:  
            - SYN flag is sent from client to server    
            - SYN/ACK flags are sent back to client from server (the SYN is now the server's SYN in order                           to make the fully established connection)    
            - ACK flag is sent back to server from client (connection is established)  

  - UDP (User Datagram Protocol)
        - lightweight, connectionless protocol
        - doesn't send acknowledgement or guarantee delivery
        - often used for voice and video apps

  - OSI (Open Systems Interconnection) Model

      - Physical Layer - wires, radios, & optics  
      - Data link Layer - data transfers between two nodes  
      - Network Layer - Internet Protocol (IP)  
      - Transport Layer - TCP and UDP  
      - Session Layer - manages the exchanges of communications between systems     
      - Presentation Layer - translates data so it can be transmitted (how to represent encryption)  
      - Application Layer - determines how users interact with data using web browsers/clients  

- IP Address 
      - Public IP - fully unique number in the world, assigned to my router by my ISP  
            - my public IP can change (dynamic IP), when restarting router or lease expires   
              * static IP addresses often used by businesses for hosting servers, VPN's, etc   
      - Private IP - assigned by my router, but is only used on my network (this # probably used millions                     of times in the world)  
      - written in the Dotted Quad Notation (4 numbers, separated by periods  
      - can range between 0-255    
        - IPv4 was used for a long time, but because the world needs more, now IPv6 is being used   
        - IPv6 is 8 groups of four hexadecimal #'s

- NAT (Network Address Translation) - the process of translating private IP addresses to a public IP                   address and vice versa  
    - basically the go between process of visiting a website   
    - obscures network size, unsolicited inbound traffic gets dropped if it doesn't specify which   
            private IP to go to   
      * you go to google.com, request goes to your router, router uses its public IP to communicate with             the internet, and then back to you (your private IP address is never seen)  

- Subnets - a way of dividing a larger network into small logical segments  
      - can divide among finance dept/general employee network/servers/guest wifi, etc.  
      - isolating each area enables network segmentation (key security control)   
      
- Subnet Mask - defines where the network portion of an ip address ends and the host portion begins  
    255.255.255.0 = means the the last number will identify the specific device   

- DHCP (Dynamic Host Configuration Protocol) - allows the automatic assignment of IP addresses from an 
      administrator-configured pool
          * DORA Process 
            - Discover: device joins network and asks if a DHCP server exists
            - Offer: DHCP sercer responds and offers an available IP address
            - Request: device takes the IP address
            - Acknowledge: server confirms the IP address is their for a set period of time 

      - Rogue DHCP Server: attacker sets up a fake DHCP server on the network
                - when devices request an IP, the rogue server assigns them a valid IP, but a malicious                       default gateway and a malicious DNS server
                        - routes all traffic and DNS queries through them (MITM attack)
            * Defense: DHCP Snooping - a switch feature that only allows DHCP responses from trusted ports

- DNS (Domain Name System) - used to connect a website name with an IP address (that computers                                               communicate with)      
      - operates over UDP port 53    
      - so when you type in a domain name, your computer sends a request to see if it's on my local                   cache, if not it asks the local DNS server (resolver) asking for the IP address associated,               if not their it asks my ISP's DNS server, and if not that, it queries up the DNS hierarchy                 until it's found  

      - DNS Spoofing/Poisoning: an attacker corrupts DNS cache with false records
            - so if you type in bank.com, the DNS server returns the attacker's IP instead, fake website  
      - DNS Hijacking: attacker modifies DNS settings on your router or device to point a malicious DNS                 server that returns false results for everything  
      - DNS Amplification: a DDoS amplification attack - attacker sends small DNS queries with spoofed                 source IP (Victim's IP) to many DNS servers. DNS servers send large responses back to the                     victim  
      - DNS Tunneling: attacker encodes malicious data or commands inside DNS queries and responses to                     bypass firewalls   
            - since DNS traffic is usually allowed through firewalls, this can be used to exfiltrate data                     or maintain command/control comms with malware     
        * DEFENSE: DNSSEC (DNS Security Extensions) - add digital signatures to DNS records so recipients         can verify the response actually came from the legitimate DNS server  (prevents spoofing/poison)    
- Network Ports - guide traffic to the correct final destination 
        * IP address is the building #, Port # is the apartment # (talk to the service @ port 80 (HTTP)
    - 16-bit binary #
      - 0-65,535
      - well known ports are between 0-1,023 (reserved for common apps & assigned by internet authority) 
      - registered ports are 1,024-49,151
      - dynamic/ephemeral ports 49,152-65,535

      * Ports:
        22 - SSH (secure remote access)
        23 - Telnet (insecure remote access - should never be used)
        25 - SMTP (email sending)
        53 - DNS
        80 - http (unencrypted web)
        443 - https (encrypted web)
        3389 - RDP (windows remote desktop - frequently attacked)
        20/21 - ftp (insecure file transfer)
        110 - POP3 (email - old approach) - once you read it on one device, its no longer on the server
        143 - IMAP (email - modern approach) - syncs email between server and device
        137-139 - NetBIOS

        NMAP - used by attackers to scan which ports are open on a target 

ICMP (Internet Control Message Protocol) - the "housekeeping" protocol  
    - Ping Command - system sends a ping command over the network, the receiving systems responds   
        - the ping command runs an ICMP Echo request   
                - the response is an ICMP Echo reply      
                * your computer reports back how long it took   
    - Traceroute - maps the actual path packets take to their destination  
    - Error reporting - telling devices when something goes wrong (destination unreachable/time exceeded)    
    - Ping Flood - overwhelming a target with ICMP echo requests - simple DoS attack  
    - Ping of Death - sending oversized ICMP packetes to crash a system  
    - Smurf Attack - uses ICMP echo requests with spoofed source IP and broadcast amplification   
    - Ping Sweeping - uses ICMP to find which IP addresses have active devices (attacker recon)  
    
  * Many orgs block ICMP at their firewalls, so attackers can't discover active hosts 
