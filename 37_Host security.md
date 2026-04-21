###  OS Security  

    - Limit admin access by using Group Policy Objects (GPO's). 
          - done in the Group Policy Management Tool. 
      
- Patch Management. 
    - corrects security issues. 
    - Linux updates: sudo apt-get update  = will obtain a list of updates available. 
                     sudo apt-get upgrade = will download and install the updates. 

- System Hardening - analyzing the default settings of your OS and removing services and  
      components not required to meet the business needs. 
        - 1) remove any unecessary software or OS components not required for functionality. 
                  - known as reducing the "attack surface". 
        - 2) lock down the host firewall to only allow access to those open ports/services needed. 
        - 3) disable any default accounts/passwords that came with the OS  
        - 4) verify that the system config settings match industry best practices. 

  ### Malware Prevention

  - Viruses - malicious code objects theat spread from system to system after human action. 
        - transported on removable media or spread by email attachments. 
        - carry a malicious payload that carries out the author's intent. 
              - stealing data. 
              - joining the system to a botnet. 

  - Worms - similar to viruses, BUT can spread by themselves  
          - NO USER ACTION NEEDED. 
          - scan networks, seeking out vulnerable systems to compromise. 

  - Trojan Horses - pretend to be legitimate, and run as expected, but contain hidden payload. 
 
  - Spyware - malware that gathers info and sends it back to author. 
            - keystroke loggers. 
 
  * Signature Detection - used by anti-malware software to search for a specific pattern of code. 
        used by known malware samples. 
          - NEEDS TO BE CONSTANTLY UPDATED!  
  * Behavior Detection - these systems monitor normal activity and then report when something. 
          abnormal happens

  - Endpoint Detection and Response (EDR) - a type of endpoint security control/platform that  
        provides advanced behavior-focused monitoring and response systems installed on devices. 
          - continuously monitors endpoint activity, detects suspicious behavior, and responds  
          - can kill malicious processes, isolate devices from network, quarantine, alert sec.  
          * can send a received suspicious executable to a malware sandbox to investigate. 

  - Extended Detection and Response (XDR) - goes further than EDR, and aggregate and correlate                 data from various sources such as endpoints, networks, servers, and cloud services. 
              - can quickly check if malware found on one system exists in other parts. 
              - incorporates AI to move quickly 
    
