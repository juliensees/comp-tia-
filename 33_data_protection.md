- Data at rest  
    - data stored for later use on storage media  
      * vulnerable to theft if hacker gains either physical or logical access  
- Data in transit  
    - data being sent over a network between two systems  
      * vulnerable to eavesdropping attacks  
- Data in Use  
    - data being actrively used in a system's memory  
      * Memory scraping - attacker uses RAM scraping malware to attack point of sale systems to steal  
          credit card data while it's being processed in RAM (before encryption)  
        --- THE HARDEST TO PROTECT, BECAUSE DATA MUST BE DECRYPTED TO BE PROCESSED! --  

- Data Security Controls  
    - Clear policies/procedures covering data use and security  
    - encryption to protect sensitive info  
    - file system permission restrictions  
          - only certain people have access  
    - geographic restrictions    
    - segmentation and other network security controls   

- Data Types

  - PII (Personally Identifiable Information) - any info that uniquely identifies individual person  
  - PHI (Protected Health Information) - protected health info, subject to HIPAA  
  - Financial Info - any personal financial records  
      - subject to Gramm-Leach-Bliley Act (GLBA) or Payment Card Industry Data Security Standard (PCIDSS)  
  - Intellectual Property - trade secrets (formulas, manufacturing processes, strategies, etc)  
  - Legal Information - documents, comms, records of legal proceedings, including attorney/client privilege
  - Regulated Information - data governed by any law or regulation
 
  -- ALL INFO, HUMAN-READABLE OR NOT... IF IT IS CONSIDERED SENSITIVE INFO, IT'S SENSITIVE INFO  

  - Data Anonymization    
        - Deidentification - process of moving through a dataset and removing data that may be                             identifying    
              - removing names, SS #'s, or other identifiers    
              * but hackers can often combine innocuous fields to eventually identify an individual    
                  ( zip codes, dates of birth, and gender)  = can identify 87% of people
        - Anonymization - removes the entire possiblity of identification

        *  HIPAA De-Identification Pathways  
            - hire statisticians to analyze your dataset and validate it's unlikely to identify someone  
                * possibility of a disclosure because giving someone else access to the info  
            - Safe Harbor - requires eliminating 18 elements from the dataset that might be combined with                 each other to reveal individual's identity (SS #, email, DOB, zip code, etc)

    - Data Obfuscation  
                - transform PII into a form where it is no longer able to tie to someone  
       - Hashing - replaces sensitive fields with hash values  
                  - one way function that can't be reversed  
                    - Rainbow Table Attack - attacker uses an original list of possibilities to check                             against repeating patterns of symbols.    
                        * a list of all students in a college, compared against hashed list of names  
       - Tokenization - replaces sensitive fields with a random identifier  
                  - keeps a lookup table (key) to later identify someone  
                         * lookup table has to be kept secure  
       - Masking - replaces the sensitive info with blanks (X's over SS #'S)    
               - permament, can't be reversed  

  - Information Classification  
      - Data Classification Policies - assign info to categories known as classifications that determine:            - storage, handling, and access requirements  
      - Security Classifications  
          - Sensitive, Confidential, Public, Restricted, Private, Critical    
      - Labeling Requirements - standard practices/markings for an org to identify sensitive info  
      - Disposal Procedures - wiping techniques before drives are thrown away/recycled  
   
### Organizations may decide to prohibit the use of cloud resources for information at certain classification levels, or use specialized security controls such as disk volume encryption
