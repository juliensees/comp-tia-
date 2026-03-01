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

Eavesdropping Attacks

    - all of these attacks require some compromise of communication between a client and a server
      - tapping into a network device or cable
      - conducting a DNS or ARP poisoning attack to trick a system into sending traffic directly to the attacker (instead of the recipient 

On-path attacks - includes MITM (man in the middle) and MITB (man in the browser) attacks because the attacker is "on the path" between the victim & server

Replay attack - when an attacker captures legitimate network traffic and retransmits it later to trick a system into accepting it as valid
      - could be an attacker re-sending valid login data that they captured earlier
      - the attacker doesn't need to decrypt anything. they're just sending the encrypted login details along 
      - DEFENSE: making each transmission unique & TIME SENSITIVE
          - token - each session established with system should generate unique token that expires after a certain amount of time
          - timestamp - rely on both systems having time set correctly so that the stolen transmission can no longer be used because it's from an older time

SSL Stripping - an attacker who can view a user's encrypted web comms, and trick the user's browser into reverting to unecrypted comms
      - strips the SSL or TLS protection 

DNS (Domain Name System) - a service that translates common domain names into IP addresses for the purposes of network routing

DNS Attacks 
    DNS Poisoning - when an attacker infiltrates the communication between DNS servers
          - they introduce false results into the communication process and thus redirect traffic to the attacker's system (can make a fake bank website)
                - they can steal login credentials this way
    Typosquatting - an attack that consists of registering domain names similar to official sites, hoping users won't recognize the typo

    Domain Hijacking - when an attacker gains control of an org's domain registration through impersonation
    URL Redirection Attacks - place content on a legitimate site that automatically forwards a user from legitimate site to a malicious site 
        - might post malicious content within a forum 
    Domain Reputation - threat intelligence capability that scores domains as either benign or malicious 

WEP (Wired Equivalent Privacy) Protocol - an easily cracked wireless network (maybe the first one?). not considered secure anymore. now WPA3 is used 
      - uses individualization vectors (which have a random value) to combine with the encryption key, in order to make the same data look different everytime
    WEP Attacks - depends on an attacker capturing initialization vectors (IVs)
            - IV's within WEP used random numbers, but they weren't random enough and repeated too often (easily hacked)

WPA (Wifi Protected Access) - adds TKIP (Temporal Key Integrity Protocol) - makes the encryption key change all the time
    - also not used anymore, only WPA2 and WPA3

WPS (Wifi Protected Setup) - allows quick setup of devices on a network
      - can press buttons on both devices to connect OR use the 8-digit WPS PIN
          - BUT THIS IS NOT SECURE!! Only 11k poossible combinations of PINS!!
                  - Vulnerable to a PIN brute force attack!
            - SHOULD TURN OFF WPS FEATURE ON ROUTERS

Propogation Attacks - when attackers simpoly use strong antennas to pull signals out of the air for analysis 
    - Jamming/interference Attacks - DoS (Denial of Service) attack that broadcasts a very strong signal to overpower the legitimate wireless access point(WAP)
    - Wardriving attack - a mobile attack where the attacker drives around a neighborhood using a powerful wireless antenna and grabs anything they can
          - usually attack weak WEP or WPA encryption, using special software that automatically captures info and correlates it with GPS data on a map
    - Warflying attack - uses aircraft, drones, or UAVs to gather network intel

Rogue Access Points - occur when someone connects an unauthorized wireless access point (WAP) to an enterprise network
  - an employee setting up a personal wireless router into the company's wired network
  - Evil Twin Attack - an attacker sets up a fake access point that mimics a legitimate one -same network name (SSID), victims connect;thinking its real
        - connecting to a rogue AP (Access Point) gives unrestricted access to the network (bypasses authentication)
              - they bypass firewalls, network access controls, and authentication systems on the wired network
        - DETECTION: wireless site surveys and WIDS (Wireless Intrusion Detection System) - scans airwaves for unauthorized AP's

Disassociation Attacks - when an attacker forces a device to disconnect from a WIFI network by sending fake disassociation frames 
          * wifi networks use management frames - control messages that connect and disconnect devices
        - an attacker sends spoofed disassociation frames to a victim's device pretending to be from the legitimate AP (access point)
            - the victim disconnects... when they reconnect, the attacker captures the WPA2 handshake that occurs during reconnection
        - disassociation attacks EXPLOIT unauthenticated management frames
              - WPA3 protects agains tthis 
            - PART OF THE "AVAILABILITY" section of the CIA triad because it first is about the availability... it disconnects you from service
                  - but they can then go further and touch on CONFIDENTIALITY, by then capturing the handshake of the password, or traffic interception
                  
Bluetooth Attack - hacker must be within 30ft of range 

  - Bluejacking Attack - when an attacker uses bluetooth to send spam messages directly to a device 
     - convinces a user to visit a website or take other action
       - not really done these days 
  - Bluesnarfing - unauthorized access to data on a bluetooth device (contacts, emails, messages, calender)
  - Bluebugging - attacker gains full control of the device over bluetooth (MOST SERIOUS!)
        - DEFENSE: turning bluetooth off, making device non-discoverable

RFID Security -  chips embedded in many tiems and may be read by RFID scanners
    - passports, tap function on credit cards, electronic toll systems, warehouse businesses etc
    - RFID Skimming - someone gets close enough to your card or badge and reads the data off it
    - Cloning - attacker reads your RFID chip data and write it onto a blank chip - creating a duplicate card
        - DEFENSE: RFID Blocking (wallets/sleeves), and encrypted RFID Chips 
