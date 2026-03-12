- Industrial Control Systems (ICSs) - the devices and systems that control industrial production/operation

     - usually less secured than traditional computing infrastructure
     - continuous operations mean less consistently patched/updated
 
  - SCADA (Supervisory Control and Data Acquisition)
      - very common in industries requiring remote monitoring of nat gas, power/distribution infrastructur  
      - usually have individual remote sensors known as remote telemetry units -report to central command
          * attacks can target feedback to central control, or cause sensor/control to perform actions
  - DCS (Distributed Control Systems)
      - common to control water/water treatment, power plants, production lines, electronics, food
      - uses a combination of sensors and feedback systems to control/adjust processes
          * attacks against PLC's (Programmable Logic Controllers) typically handle difficult
            environments with special temp, vibration, etc that if distributed can cause serious delays
              - PLC's themselves usually just have buttons, but connect to a human machine interface

### PLC's are used in SCADA AND DCS systems

    - Modbus Protocol - allows simple comms in PLC systems over the serial interfaces in industrial apps  

- Internet of Things (IoT) - any physical device that connects to the internet & collects/exchange info   
      * difficult for consumers to update the software on these devices  
      * these devices connect to home/office wireless networks -- can become a gateway for attacker  
      * if a smart device connect to cloud services, can be a pathway for attackers that bypasses firewall

  - Security Wrappers - separate code written that intercepts interactions with an app, but without
        modifying the original app
          * mainly used in legacy apps that can't be updated or 3rd party software you can't modify

  ### Network segmentation is the most important control for Embedded Systems   
      - placing untrusted devices on a network of their own, where they can't access trusted systems  
        * similar to a DMZ zone  
      - embedded systems that have web interfaces are susceptible to the same web app attacks as others   
          * SQL injection, buffer overflows, XSS Attacks (cross-site scripting)  
        * PLACE FIREWALLS IN FRONT OF EMBEDDED SYSTEMS  
  
* Main Technologies
  - System on a Chip (SoC) - combines processing, memory, networking, etc onto a single chip  
        - Raspberry Pi - miniature computer that uses a Broadcom "system on a chip"  
        - Arduino - has a simple SoC that can only perform basic actions, one at a time  
  - Field-programmable gate arrays (FPGAs) - chips that allow dynamic reprogramming  
      - eFUSE tech from IBM allows modification of these chips  
   
  - Real-time operating systems (RTOSs) - provide secure computing for IoT devices   
      - used in factory assembly lines or places where things must happen at precisely the right                       millisecond  
              - used in medical devices, industrial control systems, automotive, aviation, etc  
          * RTO Devices are usually running 24/7 and thus can't be taken offline for updates  
          * are usually run for many years, and thus sometimes legacy systems  
              * Air-gapped - so they are often not connected to networks because they are insecure  

   - CAN Bus (Controller Area Network) - a comm protocol that allows multiple microcontrollers and  
     devices within a vehicle or industrial system to communicate with each other w/o central computer  
       - devices used to have many wires connecting everything one at a time to each other  
           - with CAN Bus, everything runs through 1 or 2 wires, instead of individual connections  
               * any device can send a message and all other devices receive it  
        * No authentication - any device can send a msg, and other devices will accept as legitimate  
        * No encryption - msg travels in plaintext  
        * Infotainmnet system - bluetooth can potentially reach CAN Bus  
        * Telematics systems - GPS and remote monitoring connected to cellular networks   
