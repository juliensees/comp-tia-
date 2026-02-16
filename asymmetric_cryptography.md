RSA (Rivest, Shamir, Adleman) Algorithm
  - one of the earliest asymmetric algorithm and still used today 
  - the user selects two very large prime numbers, and they are used to create a public and private key
  - to send a message, the sender encrypts the message with the public key, and it's decrypted with the private key
  - RSA is quite slow, so it's not usually used for echanging long message
      - USUALLY USED TO CREATE AN INITIAL SECURE COMMUNICATIONS CHANNEL, AND THEN THE TWO SYSTEMS CAN EXCHANGE A SYMMETRIC KEY
  - asymmetric encryption algorithm
  - uses variable length keys between 1024 and 4,096 bits
      - 1024 bit version no longer secure! only 2048 or higher!!
   
PGP (Pretty Good Privacy) Algorithm
  - open source and private versions
  - uses both symmetric and asymmetric cryptography
  - the send has the plain text and generates a random symmetric encryption key to encrypt a message
      - then they encrypt the random key itself using the recipients public key

GnuPG
  - uses the same framework as PGP, but is fully open source

ECC (Elliptic-curve cryptography) - uses the elliptic curve discreet logarithm problem
  - DOES NOT USE THE PRIME NUMBER FACTORIZATION PROBLEM LIKE RSA

Quantum Computing - could possibly crack cryptography 

TOR (The Onion Router) - uses encryption and relay nodes to hide the true source and destination of network comms
  - uses PFS (Perfect Forward Secrecy) - hides the nodes' identity from each other by hiding in layers of nodes (layers of an onion)
  - provides traffic obfuscation, resistance to traffic tracing, and a degree of anonymity
  - usually uses 3 nodes
      - Entry Node
          - knows your real IP address, but not the website you're visiting
      - Middle Relay Node
          - passes traffic along, doesn't know original source or destination
      - Exit Node
          - knows the destination website, but doesn't know the original sender
  - NOT PERFECT ANONYMITY
      - Risks: browser fingerprinting, logging into personal accounts, malware can leak IP, malicious exit nodes
            - abuse traffic usually appears on the exit node. malicious actors, including governments may collec metadata from there
