CIA Triad: 
  - confidentiality - only authorized individuals have access
      - disclosure attacks - seek to undermine confidentiality
  - integrity - no unauthorized modification to information
    - alteration attacks
  - availability - all authorized individuals should be able to access information and systems
      - DOS (denial of service) - will overwhelm or crash a system 

### AAA - authentication, authorization, and accounting (or identification)
  - how users gain access
  - identification: a user makes an assertion (no proof needed at this point). maybe just a username
  - authentication: a user proves their identity (gives an ID). password time
  - authorization: an access control system allows access to the user.

Security Controls: procedures and mechanisms that an org puts in place to manage security risks
  - deciding your risk profile in line with the org's desired risk appetite
  - Defense in Depth: multiple controls for the same objective (in case one control fails)
      - multiple and overlapping controls
  Preventive: stops a security issue from the start
  Detective: identifies that a potential security issue has happened
  Corrective: remediates security issues that already happened  (restoring information
  Deterrent: Prevents an attacker from seeking to violate policies
  Directive: informs employees what to do if something happens
  Compensating Control: fills a known gap in a security environment

Technical Controls: using technology to achieve security control objectives (firewalls, encryption, intrusion prevention systems)
  - carried out by computers

Operational Controls: human-driven processes (user access reviews, log monitoring, background checks)
  - carried out by people

Managerial Controls: improve the security of the risk management process (future planning, project management)

Physical Controls: fences, locks, burglar alarms
  preset locks: physical locks
  cipher locks: physical keypad
  biometric lock: fingerprint, voice, or retinal pattern
  card based locks: card reader or proximity card
    Tailgaiting: one user holds the door for the next user

Gap analysis - is a comparison (maybe by a 3rd party) to see the gaps between the current and desired states of the org
    - afterwards, a road map (could be several years) to make remediation efforts for things to change
  - Desired state: know the desired state of what your org policy, HIPAA, GDPR, or PCI DSS standards are
  - Current state: where do you currently stand in terms of your security

ZTNA (Zero-Trust Network Access) - applies least privilege to network access
  - no user or device should ever be granted access based on their location on network
  - access is specific to a user's roles
  Core Principles of Zero Trust:
      - Adaptive identity - provides support for multiple types of users who roles and identities may evolve as things change
      - Threat scope reduction - supports agility and complexity while keeping the environment as simple as possible to minimize risks
      - Policy-Driven access control - provides a flexible environment tha trealizes that access needs may change, and creates a technical environment supports any policy decisions made
      - Implicit trust zones - offer easily configured zones for data that must be protected, such as personally identifiable information (PII) & credit card data
    
    Control Plane - where all the network policy decisions are made
      Policy Decision Point:
        - Policy Engine - makes the decision to grant/deny actions
        - Policy Administrator - sends configuration commands to the policy enforcement point, telling it whether to grant/deny access
    Data Plane - where those decisions are enforced and whether access is granted
        - Policy Enforcement Point - the component that intercepts requests and crosses between the data plane and control plane, and ENFORCES THEM!
    
SASE (Secure Access Service Edge) - delivers a fully integrated network with ZTNA
    - a long term goal vs ZTNA's medium-term objective
  SDN (Software-defined networking
  ZTNA (zero trust network access
  CASBs (Cloud access security brokers)
  FWaaS (Firewall as a service)

  Two-person integrity = two people must enter sensitive areas together for any access (deters theft)
  two-person control = requires the concurrence of two individuals to control access of secure functions (two keys for one activity)

Deception Technology (from the org)
  Darknets: unused but monitored IP address space that are set aside to possibly detect unwanted users 
              - nothing is ever done in these "areas", so if activity is detected it's quite possible it's an intruder
  Honeytokens: fake records inserted into databases or file systems (if someone tries to use or access these records... intruder)
              - maybe a fake e-mail address
  Honeyfiles: false stores of sensitive information (actual garbage data to distract, and intentionally provide misinformation)
  Honeypot: systems designed to attract and trap attackers, and may contain fake sensitive data, but carefully monitored
              - will immediately alert administrators
              - they send fake telemtry to the attacker and real telemtry to the security team
  Honeynets: large scale deployments of honeypots
  DNS Sinkhole: redirects malicious or unwanted domain name requests to a controlled, harmless IP address instead of their real destination
                  - returns a fake IP address (0.0.0.0), so the connection to the server never reaches the attacker
                  - self-inflicted DNS poisoning attack
              - malware that hard-codes IP address (bypassing DNS) or uses DNS-overHTTPS to an external resolver WILL NOT BE affected by the sinkhole (attacker work-arounds)

  Change management: a systematic approach to planning, implementing, and monitoring modifications to systems and processes to minimize risks/maximize benefits
      - should have a well-defined approval process (reduces the risk of unauthorized breaches)
      - every change should have an assigned owner (to know who's responsible)
      - identify and engage stakeholders - system admins, security professionals
      - conduct an impact analysis - assess potentional consequences such as risks, vulnerabilities 
      - test changes and review test results 
      - should have a back-out plan in case anything fails (reverse the changes)
      - deploy changes during planned maintenance windows (minimum impact on users)
      - adhere to SOP (standard operating procedures) - best practices and guidelines

  Changes in IT system:
    Technical implementations:
        - allow lists and deny lists control access to resources and preventing unauthorized actions and intrusions 
        - restricted activities: imposition of restrictions on certain activities 
            - disabling unnecessary services or restricting user privileges can mitigate potential vulnerabilites 
        - downtime - plan and communicate effectively to minimize disurptions during "quiet" periods
        - service/application restarts to apply modifications
        - legacy apps - changes can impact old apps that aren't updated anymore... need to make sure beforehand
        - dependencies - changes may have dependencies on other systems, applications, or components 

  Version Control - a system that tracks changes to files over time, allowing you to recall older versions/see who made changes/collaborate (an "undo" history for a project)

  
