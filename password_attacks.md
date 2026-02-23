Shadow Password File - a security feature that stores encrypted password hashes in a more restricted file
    - used in Linux/Unix systems

### All hashes are the same output, no matter how many characters are in the original

Birthday Problem - an attacker exploits the mathematical probablity to find two different inputs that produce the           same hash output
        - so they're not finding the actual original password, but a plain text pass that matches the hash (that             happens to match the hash of the actual password
            - when this happens, it's called a Collision (MD5 & SHA-1 are broken because collisions found)

Brute Force Attacks - work against short, non-complex passwords
    - can be offline, against a stolen password file or online (consistently trying to login)

Dictionary Attacks - assume people use english words and try every word with a pre-made list of plain-text passes,       and does the hashing in real time during the attack

Hybrid Attacks - use the dictionary attack but add common variations like adding a year to the end of the word

Rainbow Table Attacks - has a pre-made list of already hashed plaintext/hash pairs, so no hashing needs to happen         during the actual attack

Password Spraying - the attacker takes a list of commonly used passwords and then uses them to try to attack many       different accounts at the same time
    - BEST DEFENSE: INCORPORATE A LIST OF COMMON PASSWORDS IN ACCESS CONTROL SYSTEMS: DENY USAGE

Credential Stuffing - exploits when users reuse passwords on multiple sites

Multi-factor authentication helps all of it!
