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
            - SYN/ACK flags are sent back to client from server (the SYN is now the server's SYN in order                         to make the fully established connection)  
            - ACK flag is sent back to server from client (connection is established)

  - UDP (User Datagram Protocol)
        - lightweight, connectionless protocol
        - doesn't send acknowledgement or guarantee delivery
        - often used for voice and video apps

  OSI (Open Systems Interconnection) Model

      - Physical Layer - wires, radios, & optics  
      - Data link Layer - data transfers between two nodes  
      - Network Layer - Internet Protocol (IP)  
      - Transport Layer - TCP and UDP  
      - Session Layer - manages the exchanges of communications between systems     
      - Presentation Layer - translates data so it can be transmitted (how to represent encryption)  
      - Application Layer - determines how users interact with data using web browsers/clients  
