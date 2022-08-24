# Architecture

**Commercially Off the Shelf (COTS)** tools are available on SHIP-HATS with the right security and compliance settings. The following diagram shows how they work together to provide a seamless platform. 

![Architecture](./images/architecture.png)

<!--
The above image provides a high level architecture overview for our new SHIP-HATS2.0 platform.

- The left side of the diagram shows the user accessibility to the services we are offering 
- The middle box represents the services in SHIP-HATS 
- The right box indicates the components that are the deployment endpoints at agency hosting resources

### Key Features
- One of the new features in SHIP-HATS 2.0 is the removal of OpenVpn and SHIP credentials in existing 1.0 setup. This is replaced by TechPass and SEED, as explained in the [TechPass and SEED](#techpass-and-seed) section.  
- The central pieces are the COTS applications. As shown in the diagram, we will be hosting the resources using SaaS by the product principals. The SaaS offering has higher resiliency and faster product update to offer a greater experience to our users.
    - The initial offering will be Gitlab on SaaS. This is a SaaS instance from Gitlab that is hosted in Singapore region and it is dedicated to GovTech usage only. We have gone through all the necessary risk assessment and compliance check on this setup to ensure that we can keep our data up to *Restricted* classification.  
    - SHIP-HATS 2.0 will soon enable the cloud version of JIRA, Confluence, and Fortify on Demand at a later date. 
    - pCloudy device test farm over the cloud is already available in current setup, and it will remain as it is. 
    - The right section in the center box indicates that we have hosted the Gitlab runner that is shareable by SHIP-HATS users. These runners will gradually be replaced by Gitlab shared runners on the SaaS in near future. 
- Sonarqube, Nexus products, and Prisma Cloud applications will be moved to the SaaS version at a later dates. Refer to our product roadmap. 
    - The deployment section on the right side of the diagram indicates that the agencies can leverage on SHIP deployment runners or agent offered as a common service to the tenant hosting environments. We support GCC1 and 2, both Internet & intranet/Gen compartments. 
- Agency with on-prem resources are able to configure remote runners in their DC and can establish a connection to SHIP-HATS via IPSec Tunnel to consume our services and to perform automated deployment. 

-->


## Terminology
This documentation uses the following terminology:

| **Term** | **Description** |
| --- | --- |
|CC|Commercial Cloud|
|GCP|Google Cloud Platform|
| GSIB | Government Standard Image Build|
| GCC | Government Commercial Cloud |
|Runner  | Agents that run the CI/CD jobs that come from GitLab|
|SaaS | Whitelisted services & resources in the Commercial cloud
|SEED|Security Suite for Engineering Endpoint Devices
|Self-Hosted |  Services & resources hostesd in ship-hats GCC enviroment
| SOE | Standard ICT Operating Environment|
| VPC | Virtual Private Cloud|
| TGW | Transit GateWay|

## TechPass and SEED 

To start using SHIP-HATS 2.0 services, you must onboard to SEED and TechPass. 
SHIP-HATS Users can either access from from GSIB or GMD to authenticate yourself via TechPass login. 
Users with internet devices must onboard to SEED by installing MDM applications before they are allowed to authenticate via TechPass to consume SGTS services, including SHIP-HATS. 

![](./images/tp-seed.png)


- [SEED is an MDM application](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/) to be installed on user devices, which is a mandatory requirement to access to SGTS services. 
- [TechPass is a single sign-on IAM solution](https://docs.developer.tech.gov.sg/docs/techpass-tenant-guide/) to allow users to gain authentication and authorization to different services in SHIP-HATS as well as other SGTS subscriptions. 
