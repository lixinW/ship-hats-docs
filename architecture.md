# Architecture

The integrated CI/CD used is GitLab on SaaS is hosted in Singapore and dedicated to GovTech usage. Based on the risk assessment and compliance review, this architecture is approved to host systems with classification of **Confidential Cloud Eligible (CCE)** and below.


## SHIP-HATS Architecture

The SHIP-HATS 2.0 Architecture can be described in the following sections: 
- [Access](#access)
- [Deployment endpoints](#deployment-endpoints)
- [Runners](#runners)
- [GitLab Groups](#gitlab-groups)
- [Templates](#templates)

!> **Important:** Please note that only a limited set of services are available if you access SHIP-HATS via GSIB's Secure Internet Surfing (SIS). Services not supported via GSIB include executing any git commands. Please reach out to our team before making major ICT decisions based on the below diagram. 

![Architecture](./images/architecture.png ':size=110%')


<!--Please note that GSIB rules and policies apply as always that may lead to limited services available on GSIB. Before finalizing any changes to your environment based on the above diagram, please reach out to our team.-->

?> **Note:** The above architecture diagram represents our vision. For information on our roadmap, refer to [Upcoming features](#upcoming-features). 

## Access

SHIP-HATS 2.0 is accessible using [TechPass](https://docs.developer.tech.gov.sg/docs/techpass-tenant-guide/) & [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/) as this is the unified approach to accessing any SGTS product. 
Users can either access from GSIB or SEED-enabled developer devices to authenticate themselves via TechPass login. 

![techpass seed](./images/tp-seed.png)
 
- [TechPass is a single sign-on IAM solution](https://docs.developer.tech.gov.sg/docs/techpass-tenant-guide/) to allow users to gain authentication and authorization to different services in SHIP-HATS as well as other SGTS subscriptions. 
- [SEED is an MDM application](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/) to be installed on user devices, which is a mandatory requirement to access to SGTS services.

> **Note:** The decommissioning date for [OpenVPN is 31st, Dec 2022](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=key-tool-decommission-dates).


## Deployment Endpoints

Users can leverage SHIP-HATS deployment Runners offered as a common service to the tenant hosting environments. SHIP-HATS supports deployment to GCC 2.0, GCC 1.0, and Commercial Cloud, for both Internet & intranet/Gen compartments.


Users with on-prem resources can configure Remote Runners in their data centre and connect to SHIP-HATS via IPSec Tunnel to consume our services and to perform automated deployment.

## Runners

In SHIP-HATS 2.0 platform, there are 2 types of runners:  

- SHIP-HATS Shared Runners
- Self-hosted Remote Runners

For detailed information, refer to the [Runners](runners) topic.

## GitLab Groups

[GitLab Groups](./gitlab-groups.md ':include')

## Templates

With SHIP-HATS 2.0, we offer:  

- End-to-end CI/CD templates for [common use cases](pipeline-templates) in-line with [Gitlab pipelines](https://docs.gitlab.com/ee/ci/pipelines/). 
- Pipeline Compliance Framework to support GovTech standards & guidelines (e.g., DevSecOps IM8), on an audit-friendly platform. 

These templates are re-usable and are designed according to the standard guidelines to help agencies to follow better DevOps practices, such as GitOps workflow, bootstrapping deployment runners, and release rollback. 


Following image shows an example of production pipeline in GitLab: 

![Production Pipeline](./images/gitlab-end-to-end-pipeline.png)

<!-- We will also open up the template development for inner-sourcing. Anyone in SHIP-HATS community, expecting up to 3000 users will be able to contribute freely and to consume what others have contributed. We are hoping with more active engagement in the community is able to help the development team to accelerate their devops maturity journey. -->

<!-- One of our vision is to help agencies to comply to GovTech DevSecOps polices as stated in the IM8 document more easily, and preparing them to have an easy access to the evidence for future audit exercises. -->


> **Note:** For more information, refer to [Pipeline templates](pipeline-templates) documentation.

## Upcoming Features

[Product Roadmap](./ship-hats-roadmap.md ':include')

## Terminology

![Terminology](./terminology.md ':include')

### Related Topics

- [AWS VPC Endpoint](aws-vpc-endpoint)
- [IPsec Tunnel](ipsec-tunnel)
- [Set up GitLab Runners](gitlab-runners)
- [Pipeline templates](pipeline-templates)