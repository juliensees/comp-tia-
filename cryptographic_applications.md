### Digital certificates allow for the secure exchange of public encryption keys over otherwise untrusted networks

TLS (Transport Layer Security) - a protocol that applies other cryptographic algorithms [NOT A CRYPTOGRAPHIC ALGORITHM ITSELF]
  - uses those certificates to facilitate secure communiation over public networks
  - TLS Process;
      - the client sends a request to the server asking that the server initiate a secure session (includes a list of cipher suites)
      - the server analyzes the list of cipher suites and compares it to the server's list of supported suites
          - the server responds with it's choice of cipher suite
          - it sends the client the server's digital certificate; containing the server's public encryption key
      - the client checks what CA issued the certificate and uses the CA's public key to verify the digital signature on the certificate
          - it also verifies that the server name on the certificate matches the DNS name of the server, and that it's not expired
      - the client creates a random encryption key called the session key (symmetric encryption key) and encrypts it with the server's public key
          - the server then receives the key and decrypts it with its private key
                  - THEY CAN THEN COMMUNICATE WITH THIS AS LONG AS THEY WANT, UNTIL THE CONNECTION IS CLOSED (SESSION KEY IS DESTROYED)

### SESSION KEYS ARE THE SAME AS EPHEMERAL KEYS

### SSL (Secure Socket Layer) - the predecessor to TLS, but has flaws and not used anymore

### Cipher Suites - a combination of cryptographic algorithms that work together to (between client/server) to secure a network connection

- Blockchain - distributed, and immutable and sometimes public ledger
  - blockchain can store records in a way that distributes those records among many systems, but isn't able to be tampered with
