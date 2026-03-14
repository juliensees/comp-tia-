- Business Continuity Planning (BCP) - a collection of activities that keep a business running during adversity 

### COOP - Continuity of Operations Planning --- keeping operations running   
  - all about Availability within the CIA Triad

- Business Impact Assessment (BIA) - a risk assessment that identifies an org's essential functions, and traces those   backwards to identify the critical IT systems that support them   
      * you then get a prioritized listing of risk that could disrupt business, along with loss expectancy   

  - Single Point of Failure Analysis - process to identify and remove SPOF's  
      * could add clusters of web servers, and multiple firewalls  
   
  - IT Contingency Scenario Examples -  
       - sudden bankruptcy of a key vendor  
       - insufficient storage or compute capacity  
       - failure of a utility service  
   
  - High Availaibility and Fault Tolerance  
    - HA (High Availability) - uses multiple systems to protect against service failure  
          * REDUNDANCY!  
    - FT (Fault Tolerance) - makes a single system resilient in the face of technical failures

    - Load Balancing - uses multiple systems in an attempt to spread the demand across systems
 
   - Common Points of Failure   
      - Power Supply  
         - contain moving parts/have high failure rates... usually have backup power supplies running  
               * UPS's (Uninterruptible power supplies) also used in case of brief disruptions  
               * PDU's (Power Distribution Unit's) - provide "CLEAN" and "Managed" power  
      - Storage media  
         - RAID (Redundant Array of Inexpensive Disks) - designed to provide redundancy by having more                     disks than meets the business needs   
             - Mirroring - RAID 1 - the system has 2 disks, and stores the same data on both disks                     - Striping - RAID 5 - uses 3 or more disks using PARITY.
               - PARITY - each disk has different information, but when "paired" together, they complete                     the picture. uses calculated/mathematical formulas to store data across drives  
                       - (efficient writing/energy/storage)
                 
            * RAID IS A FAULT TOLERANCE TECHNIQUE, NOT CONSIDERED A BACKUP STRATEGY! - STILL NEED BACKUP!     
      - Networking Redundancy   
          - multiple internet service providers  
          - NIC teaming - 2 network interface cards  
          - multipath networking between servesr and their storage   
      - Platform Diversity    
          - using multiple technologies and vendors to avoid single point of failure    
          - diversity of cryptography and other security controls    
      - Multicloud operators - adds resilience as well  
    
- Disaster Recovery
