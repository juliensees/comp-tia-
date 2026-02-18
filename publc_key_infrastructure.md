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
    - is fast, and low cost
    - but both parties must keep the singular secret key safe
      - algorithm that uses a hash function and a secret key (asymmetric algorithm) and a message to                 create a secure signature/code for the message   
          - HMAC is essentially an algorithm that “signs” a message using a secret key so the receiver can                 verify two things:  
                  *Authenticity / Identity → The message came from someone who knows the secret key.  
                  *Integrity → The message hasn’t been altered in transit.  

Digital Signatures - use asymmetric cryptography to achieve:
  - authentication - the owner of the public key is the person who signed the message
  - integrity - the message was not altered after being signed
  - non-repudiation - a recipient can prove these facts to a third party if necessary
  - someone will hash their message, and then encrypt it with their private key (this is the digital sig)
      - the receiver
          - DOES NOT PROVIDE CONFIDENTITALITY
      - uses the private key for encryption and the public key to decrypt the message

DSS (Digital Signature Standard) - US standards published by NIST that supports:
  - RSA,ECDSA(Elliptic Curve Digital Signature Algorithm),EdDSA(Edwards Curve Digital Signature Algorithm)

Digital Certificate
  - X.509 - standard process for creating digital certificates  
  - contains the public key, and an expiration date, and a CN (Common Name) --like www.linkedin.com
      - can have SAN's (Subject Alternative Name) - other options covered (linkedin.com or                               rum5.perf.linkedin.com, etc)  
  - CSR (Certificate Signing Request) - a message sent from someone who wants an SSL/TLS certificate to a                 CA (Certificate Authority)     
      - it's requesting a digital certificate to later be used for HTTPS, secure e-mail, or code signing  
          - IT CONTAINS YOUR PUBLIC KEY, and identifying info, but not the private key
      * when someone wants a digital certificate, they prepare a CSR with proof of identity and send to a             CA. The CA verifies the certificate subject's identity, creates a digital certificate, signs the                     certificate with their private key, and sends it back  

Certificate Revocation - invalidates compromised certificates
  - 2 methods used by CA to revoke a digtal certificate
      - CRL (Certificate Revocation List) - puts the serial number of the certificate on this list
          - tells people not to trust a CA if it's on this list
      - OCSP (Online Certificate Status Protocol) - sends a request to the CA who issued the certificate           to verify that it's still active, and sends back a response (PUTS THE ONUS ON THE CA, INSTEAD OF             REQUESTER)
              - this does place burden on the OCSP servers operated by CA'S
   
Certificate Stapling - relieves some of the burden on CA's by validating certificates ahead of time, and               is usually valid for 24hrs  
      - a web server is basically reusing the signed certificate of anyone else who first visited the site                   and "stapling" this "old" response from the CA, to it's new response to your browser  

### CA's charge fees for their services in creating a new certificate

- Self-Signed Certificates - set up by an org for internal purposes to save money and issue their own certificates
- Certificate chaining - allows an org to have their own CA trusted by a 3rd party CA
    - Intermediate CA - name for the internal CA
    - Offline CA's - protects sensitive root keys by storing them offline (unless needed for signing certificates)

### Root CA (Certificate Authority) - exists within public or private orgs. it contains the master keys (public/private), and signs the Intermediate CA's public key with its private key to create a new valid intermediate CA cert.... then the intermediate CA can now issue end-entity certs using its own private key

- Certificate Subject - the entity that owns the public key contained within a certificate
    - servers, (web, SSH, file, email), devices (SAN's, routers, switches, VPN's), individual names/email, developers 
     - OID (Certificate Object Identifier) - a standardized way to uniquely identify certificate attributes and                   policies.  
           - identifies which signature algorithms (ex.SHA-256 with RSA), certificate extensions (Key Usage, SAN)

- Certificate Pinning - an app can be configured to only accept a specific certificate or public key for a given domain 
    - prevents Man in the Middle Attacks
    - downside is that if the certificate actually renews/reissues, the app will break until it's updated

- Certificate Types -
    - Root Certificates - the core certificates at the heart of the CA  
    - Wildcard Certificates -  
              - the "*" indicates that the certificate may be used for any subject name that uses .linkedin.com  
                - ex. *.linkedin.com  
          - but it only goes one level deep;so "secure.linkedin.com" is included, but not "www.secure.linkedin.com"  
      - using a wildcard allows the device to impersonate all the releveant subdomains without administrators having                   to obtain and install individual certificates for each subdomain
     
- CA Verification types
  - Domain validation (DV Certificates) - the CA checks the ownership record for a domain, talks to them, and issues
        - lowest level of security  
  - Organizational validation (OV Certificates) - the CA verifies the certificate subject own the domain, but also             that the name of the org purchasing the certificate matches business records  
  - Extended validation (EV Certificate) - receives docs from the certificate subject, the CA performs an extensive             investigation to verify physical existence and legitimacy of the org  
        - most secure

- Certificate Formats  
      - DER (Distinguished Encoding Rules) - binary certificate format  
          - uses .der, .crt, .cer extensions  
      - PEM (Privacy Enhanced Mail) - ASCII text versions of DER certificates (more readable than binary)  
          - uses .pem and ALSO .crt  
            - both DER AND PEM can use .crt, so you NEED to open the file to see if it's binary or text to determine 
      - PEX (Personal Information Exchange) - commonly used by windows and pfx certificates  
          - also in binary  
          - uses .pfx, .p12  
      - P7B - text format of PEX  
          - uses .p7b  
