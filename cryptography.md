### cryptography - the use of mathematical algorithsm to transform information into an encrypted form, that can't be read by unauthorized individuals

  cryptography operations:
    1) converts information from its plain text form into ciphertext (unreadable)
    2) decryption performs the reverse transformation using an algorithm to go back into plain text

   algorithm  - a set of mathematical instructions (recipes)

   encryption algorithm - have 2 inputs: the plain text message (P), and the encryption key (K)
                         - have a single output (C) - the encrypted ciphertext
      2 kinds:
            symmetric encryption algorithms - the encryption and decryption algorithm use the same secret key (similar to a password)
                  - two people can agree on an encryption key and share it
                                - usually used for BULK data encryption (FASTER TO CREATE; uses less data)
### SYMMETRIC ENCRYPTION - the key is created and must be distributed to both parties (need to transfer the key to both people... dangerous, can be intercepted) 

 * asymmetric encryption algorithms - use different keys (public key encrypts the message, and private key decrypts the message)  
                                                - but the keys come from the same pair!  
                                - usually used for key exchange and authentication  
                                              - IN DIGITAL SIGNATURES, someone "signs" it with their private key, and it's decrypted with the public one  
                                                    - this proves that the secure message wasn't altered  
                                       * General Rule of Thumb               
                                          Public key → lets people send secrets TO you  
                                          Private key → lets you prove something came FROM you  

### ASYMMETRIC ENCRYPTION - the public key is shared, but the private key only exists on the personal computer, so it doesn't have to go anywhere

  - i download an app or a certificate that has software that gets a public key from someone else and creates my private key (and stays locally/never leaves)

  ### ENCRYPTION MAKES SOMETHING SECURE, BUT AUTHENTICATION PROVES PROOF OF ORIGIN! --- SOMEONE MIGHT HAVE A KEY, BUT DOESN'T PROVE THEIR IDENTITY

  decryption algorithm   - have 2 inputs: the ciphertext (C), and the decryption key (K)
                          - have a single output (P) - the plain text message

  Goals of Cryptography
    - Confidentiality: no unauthorized access
        - Data at rest: stored on a hard drive or storage device
        - Data in transit: transmitted over a network connection
        - Data in use: processed actively in memory (RAM)
    - Integrity: no unauthorized changes to the data
    - Authentication: proof of identity claims
    - Obfuscation: hiding sensitive data 
    - Non-Repudiation: the recipient of a message can prove to an independent third party that the message came from the alleged sender
        - digital signatures prove the original sender
        - only possible with asymmetric algorithms

### One missing piece in an encryption algorithm will make it entirely faulty

Security through Obscurity - security of an algorithm depends upon the secrecy of its approach
  - SECRECY SHOULD NEVER BE THE ONLY SECURITY CONTROL!! SECURITY THROUGH OBSCURITY WILL EVENTUALLY BE LEAKED!
      - DEFENSE IN DEPTH - THE BEST SECURITY APPROACH! MULTIPLE LAYERED SECURITY! SOME PRIVATE (OBSCURITY) BUT SOME PUBLIC!
   
Algorithm length - the longer the key length, the higher the security
                 - but the longer the key length, the lower the performance (speed goes down, too much processing)

cryptographic lifecycle - eventually algorithms become insecure due to discovered flaws or the key link becomes vulnerable to brute force attacks
    - NIST (National Institute of Standards and Technology)
      - 1) Initiation - the org realizes it needs a new cryptographic system and decides the levels of confidentiality/integrity/availability objectives
          1) Integrity of keys. authentication, authorization and nonrepudiation should be supported 
          2) Availability of security mechanisms/features at least 99.5% of the time. responsive and adaptable systems and short response times
          3) Integrity and Authentication like digital signatures to validate signers of a message and integrity of info received 
      - 2) Development and Acquisition - finding an appropriate combo of software, hardware, and algorithms that meet the objectives (mostly acquired)
      - 3) Implementation and Assessment - configure the system for use and assesss whether it meets the objectives
      - 4) Operations and Maintenance - org ensures the continued secure operation of the crypto system
      - 5) Sunset - the org stops using the system and destroys or archives sensitive material such as keys 

Deidentification - the process of moving through a data set and removing data that may be individually identifying (CAN BE LINKED BACK LATER!)
  - this process helps protect against accidental disclosures of PII during breaches
  - but technically "programs" can combine zip code, date of birth, and gender to coalesce information together to identify 87% of people
    
  HIPAA DE-identification Standard Methods
    Expert Determination - have statisticians analyze your data set and validate that it would be unlikely it could disclose identity of individuals
        - but this pathway makes it possible of an accidental disclosure (bringing in professional statisticians)
    Safe Harbor - requires the removal of 18 data types of identifiers

Anonymization - remove the possiblity of identification (CANNOT BE LINKED BACK!)
  - used in public datasets, health info for research purposes, data sharing with third parties
        - you can aggregate info about people within a city, but you don't need to know who they are

Data obfuscation - transforms PII into a form it is no longer possible to tie it to a person
  - Hashing - replaces sensitive fields with hash values
    - when you input a password,the system is actually matching the hash values to each other,not the plain text(the original plain text is gone from server!)
  - Rainbow Table Attack - compares hash values with precomputed hashes
     - the attacker uses precomputed hash databases to reverse password hashes quickly.
     - Each hash algorithm has its own table
      - "salting" adds an extra string to these hashes (random values) and is a modern way of making a rainbow table attack unusable
              - used for passwords/stopping possiblity of rainbow tables
              - if stolen, a hashed password could technically maybe be cracked mathematically later
      - Tokenization - replaces sensitive fields with a random identifier
              - used more for credit cards/payment processing
              - if stolen, each value is RANDOM, and thus meaningless... UNLESS THE TOKEN VAULT IS ALSO STOLEN!!
      - Masking - redacts sensitive info from a file
              - 

