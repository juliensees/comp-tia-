Cloud Controls Matrix 
    - a security framework for cloud computing; provides a set of security control
    - created by CSA (Cloud Security Alliance) 
    - shared responsibility model (what provider vs client vs partner orgs are responsible for)

Cloud Deployment Models 

   * Private Cloud - org uses a dedicated cloud infrastructure that isn't shared with other orgs
   * Public Cloud - uses the massive cloud provider infrastructures in their data centers
           - the same physical hardware is used for different customers
   * Hybrid Cloud - uses public for some things and private for others (more sensitive)
   * Community Cloud - universities might pool resources and create shared computing resources

### No cloud model is inherently superior!! Each has its own benefit.

### In Public Cloud, client & provider are responsible for security. Client must set security controls, while provider must encrypt data and implement access control policies 

XaaS (Anything as a service) 

  IaaS (Infrastructure as a Service)
        - customers purchase basic computing resources to piece together to create customized IT solutions
            - might combine compute capacity, data storage, and other building blocks
                - AWS, Azure, and Google Compute platform
        * client manages most (OS, apps, encryption), provider just manages hardware/network infrastructure

  PaaS (Platform as a Service)
        - customer purchases a platform to run their own application
        * client manages apps and data, provider manages the rest 

  SaaS (software as a service) 
        - customer purchases an entire app from the public cloud provider, that writes the app, configures             the servers and gets everything running for the customer
            - usually accessed through a web browser with no configuration needed (dropbox, microsoft 365)
                - also more specialized, like credit card processing and travel/expense report management
        * client manages data and access, provider manages the rest 
                
  FaaS (Function as a Service)
        - also known as serverless computing
        - instead of an entire app, it's just performing an individual function when needed 
        * client manages just code and permissions

  Security and Privacy Concerns
    - same principles of the CIA triad (confidentiality, integrity, and availability)
      * also Privacy - the right of individuals to control their personal data (stronger in europe)
    - Governance - help an org work through existing and planned cloud relationships to ensure they                 comply with security, legal, business, and other constraints (vet potential vendors, manage               relatoinships, and oversee cloud ops
    - Audibility - cloud computing contracts specify the customer has the right to audit cloud provider
            - could be on a scheduled or unplanned basis to make sure provider is meeting security 
    - Regulatory Oversight - HIPAA, FERPA, PCI DSS regulations to make sure the provider is compliant 
    
  Data Sovereignty 
    - cloud providers intentionally distribute customer data to many different locations in order to                 protect against regional failures
      - thus depending on where the data is stored, there are different laws in that area
        - so US data stored in the EU will apply to the US and EU laws
    - an org should have the provider put storage locations in writing, and deny the provider access to             an org's decryption key

    Operational Concerns
        - Availability - cloud performance = what % is the service up and running/meeting customer needs
        - Resiliency - ability of cloud infrastructure to withstand disruptive events 
          - could use redundant servers to protect against failure of a single server or many data centers
        - Performance - how well can it hold up in busy periods
          - SLA (Service Level Agreement) - documents vendor obligations and has financial penalties 

        Reversibility 
            - if something goes wrong, can a transition be reversed?
        Portability
            - maintaining flexibility to move workloads between cloud environments & avoid vendor lock-ins
        Interoperability
            - ability of different systems to work together without moving anything, just communicating 
                - your org uses microsoft 365 and your client uses google workspace (need to share docs)
                - relies on standardized API's
            - SaaS and PaaS products 
