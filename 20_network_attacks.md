CIA - Confidentiality, Integrity, Availability 
  - most common motivation is data theft (confidentiality)
        - CC #'s, SS #'s

    - DOS (Denial of Service) attack - knocks a system out, making it unavailable (VIOLATES AVAILABILITY!! THIRD PIECE OF CIA)
        - they require a large amount of bandwith, sending lots of requests that tie up the server (thus needing a large network connection)
        - simple DoS attacks are easy to block (a victim can just block the IP address of the attacker)
     
    - DDoS (Distributed Denial of Service) Attack - when  DoS attack leverages a botnet to overwhelm a target
        - difficult to distinguish between legitimate requests
        - Smurf Attack - instead of flooding with botnets, the attacker gets the victim's own devices on their network (computers, routers,                                 printers,etc), to attack themselves
              - IP Spoofing - the attacker makes it look like the victim send the ping request (so all devices send pings back to the victim network)
              - Broadcast Amplification - when you send data to the broadcast address
                    - Broadcast Address - it's the main address on the server, and so everything on the server is contacted to it (contacts everyone)

        - Amplification Factor - the degree of amplification that happens in an attack
     
    DoS Variants
      - network attacks, application attacks, or Operational Technology (OT)
