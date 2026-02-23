SQL (Structured Query Language) - used by relational databases that allow users and apps to create, update,         delete, and retrieve data

SQL Injection - when an attacker inserts malicious SQL code into an input field to manipulate the database       behind a website
        - basically a hacker puts in SQL code ("admin" into username field) in a user input form (SQL                 query), and they get to login as an admin without knowing the password because the query                       changed into thinking it had to follow the coding command and not be a normal username/                      password query 
        
*Prevention techniques of a SQL injection attack
  Input Validation - protects against unsafe user input by checking it on the server before executing               commands 
            - a username should only contain letters and numbers, so someone typing admin-- won't work
  Parameterized SQL - precompiles SQL code on the database server to prevent user input from altering               query structure
            - makes it so inputs into a query can only be interpreted as plain text and never code
            - STRONGER SECURITY than input validation, but the BEST is when both are used

  Cross-Site Scripting (XSS) - occur when an attacker embeds malicious scripts in a third-party website                 that are later run by innocent visitors to a site 
          - attacks the user/browser, NOT the server
            - dangerous because they happen without the knowledge of the victim
            - Session hijacking (stealing cookies) is a common goal
        * Prevention - Use Input Validation again -- don't allow users to insert script code into inputs

  Request Forgery - CSRF, XSRF, or "sea surf" are all the same attack
      - cross-site request forgery attacks leverage users having authenticated sessions between different             browser tabs by tricking a user's browser into sending illegitimate requests to another site 
          - it exploits trusted sessions (session cookies from you already logging in)
      * Defense against CSRF
        - Rearchitect web apps
        - prevent the use of HTTP GET requests
        - advise users to log out of sites
        - automatically log out users after an idle period

  Server-side Request Forgery (SSRF) - targets servers, by manipulating servers into retrieving malicious           data from what it believes to be a trusted source 

  Buffer Overflow Attacks - when an attacker sends more data than a program expects (enter room number for       your hotel, and put 4,500,000, and the server "overflows" into adjacent memory
      - more common in older C+ programs 
        * Defense - Input Validation

  Cookies - track user activity on the web stored in user browsers by websites
      Session hijacking - when an attacker steals your session cookie through XSS or sniffing and                 impersonate you without needing your password (server sees a valid cookie)
      * Defense - HttpOnly flag - cannot be accessed by javascript (protects against XSS)
                - SameSite flag - cookie is only sent with requests from the same site (protect from CSRF)

      Cookie Guessing - if cookie values are not randomly generated, they can be figured out
      Session replay - possible if cookie values are not encrypted in transit 
        * Defense - administrators should always send cookies using encryption

Code Execution Attacks - occur when an attacker exploits a vulnerability in a system that allows the             attacker to run commands on that system
    Arbitrary Code Execution - when an attacker can run any code they want on your system
    Remote Code Execution - do the same remotely 
    * Defense: Limit administration access, Principle of Least Privilege!
                - patch systems and apps

Privilege Escalation Attacks - use normal accounts and transform them into having admin rights
  - often exploit buffer overflow vulnerabilities
    * Defense: Input Validation on all input from end users
    * latest security patches
    * Principle of Least Privilege
   
OWASP Top Ten- Open Worldwide Application Security Project - maintains a list of common web security               issues, and best practices to deal with them
  - broken access control - when developers fail to check on the backend whether a user is authorized to         access a particular function of an app 
  - cryptographic failures - when an insecure web app accidentally exposes sensitive info publicly 
  - injection attacks - when an attacker is able eto insert code into a request sent to a website, and           then pass the code along to a backend server where it's executed (SQL injection)
  - insecure design - when an org doesn't meet security requirements or follow best practices 
  - security misconfigurations - occurs when web apps have an error in their security settings
  - vulnerable and outdated - when web developers use components that have known vulnerabilities
  - identification & authentication failures-flaws in the mechanisms of authentication (session hijacking)
  - software and data integrity failures - when an org doesn't perform appropriate verification checks
  - security logging and monitoring failures - when they don't create detailed logging efforts
  - server-side request forgery-occur when an attacker tricks a web server into retrieving unvalidated URL

Application Hardening - testing software to make sure it's safe from attack
    - use proper authentication
    - encrypt sensitive data 
    - validate any user input that might jeopardize anything
    - avoid and remediate known exploits
    - deploy obfuscation and camouflage to hide source code details from reverse engineering

### Prompt patching is critical!! - attackers quickly exploit new vulnerabilities

Application Configuration  - configuration baselines allow quick indetification and remediation of security
  - type and scope of encryption
  - users with access to the application
  - scope of access for authorized users
  - - security of underlying infrastructure
   
Directory Traversal - when an attacker manipulatese file path input to access files and directories outside of where they're supposed to be
      - they use "../" to go to other directories
      * Defense: Input Validation - can't put that in a query!!

Race Condition - occurs when the proper functioning of a security control depends upon the timing and sequence of events, and an attacker manipulates that timing
  - TOCTOU (Time to Check to Time of Use)
        - Time of check - the system checks if something is allowed
        - Time of Use - the system actually does it
          * The vulnerability is the gap between those moments
    * Defense: locking mechanisms that prevent other processes from accessing a resource while it's used
