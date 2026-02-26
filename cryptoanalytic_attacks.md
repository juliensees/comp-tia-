Brute-force Attack - the attacker repeatedldy guesses keys until they gain access  
    - the attacker only needs to have an example of encrypted text in order to "Attack"  
    - also known as "known ciphertext attacks" -- due to the attacker using minimal ciphertext to make the attack  
        - weak passwords and stolen hash databases are the most common way that hackers can still use these attacks  

### Modern systems keep out brute force attacks with strong passwords, account lockouts (3 tries and account locks), MFA, and salting hashes

Keyspace - the set of all possible encryption keys usable with an algorithm  
    - so if you're using the english alphabet, and you shift one change from A's now showing B's... in total, you only have 25 possible keys before it             just starts over  
    
Knowledge Based Attacks - attacks that go beyond the simplicity of brute force and combine other info    
        - Frequency Analysis - the person trying to break the code does some statistical analysis of the ciphertext to detect patterns    
            - for example seeing the same letter repeatedly in ciphertext and corresponding that to common english letters    
        - Chosen Plaintext Attack - when an attacker has access to the encryption algorithm and tries inputing things into it, to reverse engineer it  
        - Birthday Attack - when an attacker searches for possible collisions in a has function that may allow an attacker to exploit that function   

Limitations of encryption algorithms   

  - Asymmetric encryption are much slower than symmetric algorithms  
  - longer the key, more resistant it is, but requires more computing power (take longer to perform encryption/decryption)  

Entropy - means randomness (how unpredictable and random something is)  
  - High entropy = more random = more secure  
  - Low entropy = more predictable = less secure  

Downgrade attacks - when an attacker convinces a system to use an older/weaker/less secure version of a protocol or encryption instead of a modern one  
        - they exploit backward compatability   
  - Poodle Attack - forced browsers to downgrade from TLS to the old vulnerable SSL 3.0 protocol  
  - Beast Attack - exploited weaknesses in older TLS versions by forcing their use  
  
