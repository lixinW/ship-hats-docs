# Architecture

The integrated CI/CD used is GitLab on SaaS is hosted in Singapore and dedicated to GovTech usage. Based on the risk assessment and compliance review, this architecture is approved to host systems with classification of **Restricted and below**.


The SHIP-HATS 2.0 Architecture can be described in the following sections: 
- [Access](#access)
- [Deployment endpoints](#deployment-endpoints)
- [Runners](#runners)
- [GitLab Groups](#gitlab-groups)
- [Templates](#templates)


![Architecture](./images/architecture.png)

?> The above architecture diagram represents our vision. For information on our roadmap, refer to [Upcoming features](#upcoming-features). 

## Access

SHIP-HATS 2.0 is accessible using [TechPass](https://docs.developer.tech.gov.sg/docs/techpass-tenant-guide/) & [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/) as this is the unified approach to accessing any SGTS product. 
Users can either access from GSIB or SEED-enabled developer devices to authenticate themselves via TechPass login. 

![](./images/tp-seed.png)
 
- [TechPass is a single sign-on IAM solution](https://docs.developer.tech.gov.sg/docs/techpass-tenant-guide/) to allow users to gain authentication and authorization to different services in SHIP-HATS as well as other SGTS subscriptions. 
- [SEED is an MDM application](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/) to be installed on user devices, which is a mandatory requirement to access to SGTS services.

> **Note:** The decommissioning date for [OpenVPN is 31st, Dec 2022](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=key-tool-decommission-dates).


## Deployment endpoints

Users can leverage SHIP-HATS deployment Runners offered as a common service to the tenant hosting environments. SHIP-HATS supports deployment to GCC 2.0, GCC 1.0, and Commercial Cloud, for both Internet & intranet/Gen compartments.


Users with on-prem resources can configure Remote Runners in their data centre and connect to SHIP-HATS via IPSec Tunnel to consume our services and to perform automated deployment.

## Runners
In SHIP-HATS 2.0 platform, there are 3 types of runners:  

- **SHIP-HATS hosted Shared Runner:** The shared runners are hosted by the SHIP-HATS team. There are 3 variants in the shared runner pool. These runners are easily accessible to users and are scalable on demand.

    |Runner Variant|Executor|Privileged|Cache Enabled|Run Untag|Notes|
    |---|---|---|---|---|---|
    |CStack Runner|kubernetes|FALSE|YES|YES|Run as non-root
    |Docker Runner|docker+machine|FALSE|YES|NO|We have removed privileged access for SHIP-HATS shared runner. This affects build of systems that used the shared runners with docker-in-docker. Alternatively, you can use Kaniko.
    |Windows Runner|shell|N/A|YES|NO|- OS: MS Windows Server 2019 Base<br>- Git: 2.36.1<br>- Visual Studio 2022 version 17.0<br>- .Net framework 4.8 development tools

- **Agency-hosted Remote Runner:** The agency-hosted remote runners are the dedicated machines that are set-up and managed by agencies. These runners can connect to SHIP-HATS via the *IPSec tunnel* or *VPC endpoint* if they are hosted on GCC AWS or CC AWS. 
- **GitLab Shared Runner on SaaS:** The GitLab shared runner on SaaS will be available over the next couple months. 

<Image>

For more information, refer to the [GitLab Runner](https://docs.gitlab.com/runner/) documentation.

## GitLab Groups

Gitlab allows groups and multi-level subgroups. The subgroups enable access control for multi-tenancy. 

The first three levels of subgroups are managed by SHIP-HATS. The first-level subgroups are the root level groups for WOG, the second-level subgroups are grouped by agency names, and the third-level subgroups are offered to our subscribers (e.g. project initiative name, department, or division name). Based on your requirement, SHIP-HATS team will create and manage these for you.   
**After the third-level groups are created, you will have the permission to create and manage any subsequent subgroups within it.**  

Gitlab subgroups have the inheritance characteristic from the parents. For more information, refer to the GitLab [groups](https://docs.gitlab.com/ee/user/group/index.html) and [subgroups](https://docs.gitlab.com/ee/user/group/subgroups/) documentation. 

![User Grouping Strategy](./images/user-group-strategy.png)



## Templates

With SHIP-HATS 2.0, we offer:  

- End-to-end CI/CD templates for [common use cases](pipeline-templates) in-line with [Gitlab pipeline COE](https://docs.gitlab.com/ee/ci/pipelines/). 
- Pipeline Compliance Framework to support GovTech standards & guidelines (e.g., DevSecOps IM8), on an audit-friendly platform. 

These templates are re-usable and are designed according to the standard guidelines to help agencies to follow better DevOps practices, such as GitOps workflow, bootstrapping deployment runners, and release rollback. 


Following image shows an example of production pipeline in Gitlab: 

![](./images/gitlab-end-to-end-pipeline.png)



<!-- We will also open up the template development for inner-sourcing. Anyone in SHIP-HATS community, expecting up to 3000 users will be able to contribute freely and to consume what others have contributed. We are hoping with more active engagement in the community is able to help the development team to accelerate their devops maturity journey. -->

<!-- One of our vision is to help agencies to comply to GovTech DevSecOps polices as stated in the IM8 document more easily, and preparing them to have an easy access to the evidence for future audit exercises. -->


> **Note:** For more information, refer to [Pipeline templates](pipeline-templates) documentation.

## Upcoming features

|Items|GA (Jan’23)|Future Releases|
|---|---|---|
Runners|SHIP-hosted runner<br><br>Agency hosted runner|Gitlab Shared runners
Deployment (common service)|GCC* 1.0 (Internet)<br><br> GCC* 1.0 (Intranet)<br><br>GCC* 2.0 (non-GEN/GEN)|Agency On-prem (DC)<br><br>Commercial Cloud (CC)<br><br>GCC 2.0 GCP|
Automated Testing (Runtime)|Internet, non-GEN|Intranet, GEN|
E2E Pipeline Template|Support common use cases|Mature with inner-sourcing contributions
Compliance Pipeline|Limited coverage|Comprehensive, with SLSA framework, DevSecOps Policy
DevOps Maturity Metrics|Preliminary|Continuous development on VSM

*AWS & Azure

<!-- SaaS Applications|GitLab|JIRA, Confluence, Fortify on Demand, Sonatype
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
|Self-Hosted |  Services & resources hosted in ship-hats GCC environment
| SOE | Standard ICT Operating Environment|
| VPC | Virtual Private Cloud|
| TGW | Transit GateWay|

### Related topics

- [AWS VPC Endpoint](aws-vpc-endpoint)
- [IPsec Tunnel](ipsec-tunnel)
- [Set up GitLab Runners](gitlab-runners)
- [Pipeline templates](pipeline-templates)
