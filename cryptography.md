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
                                       General Rule of Thumb             
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
        
