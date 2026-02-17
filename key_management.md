Symmetric algorithms - two parties share a singular secret key

Out-of-Band key exchange - uses a different channel to transfer the key
  - in person
  - USB drive (physical mail)
  - telephone
      - DOWNSIDE IS OBVIOUS TIME CONSTRAINTS
   
In-Band Key Exchange
  - securely exchange keys digitally

Diffie-Hellman Key Exchange Algorithm
  - Secure key exchange over an insecure channel, without transmitting the key itself.

Diffie-Hellman Ephemeral
  - creates a new key every session (more expensive, but more secure)
  - uses Forward secrecy (also called Perfect Forward Secrecy) (PFS)
      - means that past sessions stay safe even if your long-term key is compromised in the future.

  Elliptic Curve Cryptography (ECC) — uses DLP on elliptic curves, where it's even harder per bit
   - more efficient because it uses fewer keys (less processing time)

Key Escrow
  - a key management concept where keys are stored with a trusted third party
  - like bank escrow; it means that someone is holding something for use by someone else if certain conditions are met
  - governments have wanted to have their own key escrow (in order to break into things), but it hasn't happened yet
      - Recovery Agents - used for password recovery, like Microsoft Windows Encrypting File System
          - there is a master key
       
Key Stretching - an algorithm takes a relatively insecure value (common password) and manipulates it to make it stronger
  - slows down brute force attacks by making the possiblity of breaking a password very difficult
  - 1) combines encryption keys with salting (adding a value to the encryption key)
  - 2) it then hashes the resulting value to add time to the key checking process by requiring more math
       * PBKDF2 (Password-Based Key Derivation Function 2) - an algorithm that performs key stretching
           - most people recommend using the function at least 4,000 times to make secure
        * bcrypt - based on the blowfish cipher
              - also a key stretching program

Hardware security modules (HSM's) - special purpose devices that manage encryption keys outside of the Operating System
  - expensive to purchase and operate
  - Cloud services use HSM's internally for their own management
  - certificate authorities (CAs) use them to protect root keys, banks use them for PIN processing, and enterprises use them for managing encryption keys at scale. If a question mentions a CA needing to protect its private key, HSM is the answer.

TPM (Trusted Platform Module) is a chip soldered onto a motherboard, tied to one specific device, mainly used for disk encryption (like BitLocker) and boot integrity. 

### TPM is a single device, HSM's are used for an entire network

