- Restricting access to networks:
    - Network Perimeter Security - admins want to keep unwanted users out of the network
      * firewalls with ACL's (access control lists)
    - Physical Network Access - limited to authorized users and devices
 
        - Rule Based - restrict access based upon business logic
        - Role Based - restrict access based upon the identity of an individual
        - Time Based - restrict access based upon business hours
        - Location Based - restrict access based upon physical location
     
- Network Access Control (NAC)  
    - intercepts network traffic coming from unknown devices and verifies user is authorized for comms  
      * NAC technology is used to actually scan employees personal device they're using to make sure:  
          * antivirus is installed  
          * OS is patched and up to date  
          * device is encrypted  
         - uses Zero Trust - always verifies, even if it's an employee... computer could be compromised!!  
        * uses an authentication procol called 802.1x to perform access control tasks  
            - Supplicant - the user (their device or connection software) that wants to connect to network  
            - Authenticator - network device controlling access (switch or WAP)  
            - Authentication Server - usually a RADIUS server that verifies supplicant's credentials  
                  - has other authentication jobs, but one of them is Network Access Control  
      * Role-Based Access - after user is authenticated, decides where to place user on the network  
            - student will be on one VLAN, and professors on a different VLAN  
      * Posture Checking (Health Checking) - NAC technology that verifies devices comply with the org's                       security policy before granting broad access  
                  * antivirus software has current signatures  
                  * device has properly configured firewall  
                  * device contains recent security patches  
                      - IF FAILS, MIGHT BE PLACED IN QUARANTINE NETWORK  
          - Agent-Based - software agent installed on the device that reports security status to NAC  
          - Agentless-Based - uses network scanning and other techniques to scan externally   
          - In-Band Approach - NAC device is involved in making/enforcing access control decisions   
          - Out-of-Band Approach - NAC device makes enforcement decisions, but network switch or WAP or                     other components enforce the decision  
