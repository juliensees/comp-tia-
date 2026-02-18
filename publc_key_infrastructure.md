Public Key Infrastructure (PKI)
  - depends on highly trusted certificate authorities (CA's)
    - CA's are trusted third-party orgs that verify the identity of individuals or orgs and then issue digital certificates containing both identity info and a copy of the subject's public key
      - identity cards of the digital world
          - need to provide proof of identity
    - doesn't encrypt your traffic, just validates identity and signs certificates of authenticity 

### every HTTPS website has a certificate, authenticated by a CA (around 100-150 root CA's come on the browser). HTTP DOESN'T NECESSARILY

### my browser is saying i trust the CA that verified this website... not the website itself

Hash function - a one way function that transforms a variable length input into a unique fixed length output
  - one way - can never be reversed
  - depending on each function, it always outputs the same length (SHA-256 is always 256 bits)

### All modern password systems add salting to hash functions
  - makes password storage more secure by adding random string to the end of your password
      - this way, if someone hacks into the system, your password can never match another password, and thus makes it much more difficult for a hacker to use rainbow tables or guess the password, since it has this addendum to it
      - when you login in next time, the server adds the salting characters to the end of your password and then hashes it, to see if it matches the hashed & salted password that's in the system

  Message Digest 5 (MD5) - produces 128-bit hashes and is no longer secure
    - message digest is another term for hash

  SHA (Secure Hash Algorithm) - created by the US government within NIST
    SHA-2 (second edition) - consists of SHA-224, SHA-256, SHA-384, and SHA-512 bit hashes
      - quite secure, but still has flaws
    SHA-3 - produces hashes of user-selected length

  RIPEMD - created as a non-government sponsored hash system 
    - produces 128, 160, 256, and 320-bit hashes
      - 128 not used, but 160 is used a lot in Bitcoin

  HMAC (Hash-based Message Authentication Code) - combines symmetric cryptography and hashing  
    - provides authentication and integrity  
    - algorithm that uses a hash function and a secret key (asymmetric algorithm) and a message to create   a secure signature/code for the message   
      - HMAC is essentially an algorithm that “signs” a message using a secret key so the receiver can                 verify two things:  
              *Authenticity / Identity → The message came from someone who knows the secret key.  
              *Integrity → The message hasn’t been altered in transit.  
