# Onboarding to SHIP-HATS

The following topic provides details for **onboarding to SHIP-HATS**.

!> **Natasha change all links and add missing topics in Getting Started itself.**

![](./images/onboarding-end-to-end-flow.png)

## Step 0: Pre-onboarding

|Tool|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|
|---|---|---|---|
NA|Understand technical considerations for GitLab|Technical POC|[Technical Considerations](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/migration-checklists?id=technical-considerations)
NA|Decide on base package + add-ons|Agency PM|[Subscription](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/subscription)<br><br>[Tooling strategy](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ship-hats-tools?id=tooling-strategy)
NA|Raise Internal AOR for 2.0 Tools & Services|Agency PM|[Sample AOR (Accessible to Public Officers via intranet](https://go.gov.sg/sh2indicative)
NA|Raise Vendor SR (as applicable)|Agency PM|NA|
[TechPass](https://portal.techpass.gov.sg/public/home)|Sign up for TechPass|All|[Onboard to TechPass](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/onboard-public-officers-using-non-se-machines)


## Step 1: Subscribe to SHIP-HATS

?> Complete these steps in the **[TechBiz Portal](https://portal.techbiz.suite.gov.sg/)**.


|Tool|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|
[TechBiz Portal](https://portal.techbiz.suite.gov.sg/)|Log in to the TechBiz portal|Agency PM|[Log in to TechBiz portal](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/log-in-to-TechBiz-portal)
||Create Subscription Package|Agency PM|[TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/techbiz-account)<br><br>|[Request for TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/request-for-techbiz-account)
||Approve Account|DD or above|[Approve or reject TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/approve-or-reject-techbiz-account)
||Create System Name|Agency PM|[Manage TechBiz system](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/manage-techbiz-system)<br><br>[Create TechBiz system](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/create-techbiz-system)
||Add and configure products|Agency PM|[Add and configure products](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/add-and-configure-products)
||Create Users & Grant Access|Agency PM|[Manage user access for subscribed SGTS products](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/manage-user-access-subscribed-sgts-products)<br><br>You must add users for each of the subscribed tools.

## Step 2: Onboard to SHIP-HATS

?> Complete these steps in the **[SHIP-HATS Portal](https://portal.ship.gov.sg/)**.


|Tool|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|
[SHIP-HATS Portal](https://portal.ship.gov.sg/)|Access SHIP-HATS Portal|Agency PM & Technical POC|[Access portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/access-ship-hats-portal)
||Verify Users and System (s)|Agency PM & Technical POC|[Manage users](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-users)
||Create project and assign PA|Agency PM & Technical POC|[Manage projects](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-projects)<br><br>[Manage admins](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-admins)
||Add Projects and Tools|Agency PM & Technical POC|[Manage projects](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-projects)
||Set up GL tool (and other tools as per your subscription)|Technical POC|[Manage tools](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-tools)


## 3 Configure GitLab

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.

|Tool|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|
[GitLab](https://sgts.gitlab-dedicated.com/)|Verify user mapping|Technical POC|1. In SHIP-HATS Portal, click **GitLab group.** <br><br>2. In GitLab, Click **Subgroup information** > **Members**
||Set up SSH keys|Technical POC|[Communicate using SSH keys](https://docs.developer.tech.gov.sg/docs/ship-hats-tools/gitlab/communicate-using-ssh-keys)
||Set up and GPG keys|Technical POC|[Sign commits with GPG](https://docs.developer.tech.gov.sg/docs/ship-hats-tools/gitlab/signing-commits-with-gpg)

## Step 4: Configure Pipelines

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.

|Tool|Activity|Description|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|---|
[GitLab](https://sgts.gitlab-dedicated.com/)|Set up Remote runners [Optional]|1. If you are using SHIP-HATS shared runners, you can skip to the configure CI Pipeline step|Technical POC|[Migration Checklists](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/migration-checklists?id=shared-runner-considerations)
|||2. If you are using Remote runners, you can connect to SHIP-HATS using "AWS VPC Endpoint" or "IPsec Tunnel"|Technical POC|[AWS VPC Endpoint](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/aws-vpc-endpoint)|Technical POC|[IPsec Tunnel](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ipsec-tunnel)
||Configure CI pipeline|1. Copy the E2E template into your own repository and update the project variables|Technical POC|[E2E Templates](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=list-of-templates)
|||2. Modify your pipeline using the Modular template|Technical POC|[Common Templates (Modular)](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=list-of-templates)<br><br>This is an optional step. If the E2E template does not meet your requirement, you can modify your pipeline using the Modular templates for any additional capabilities.
|||3. Apply Compliance Framework|Technical POC|[Compliance Framework](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/compliance-framework)
||Configure CD pipeline <br><br>(non-production)|1. Non-production: Execute deployment successfully|Technical POC|[E2E Templates](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=list-of-templates)
||Configure CD pipeline <br><br>(production)|2. Production: Execute deployment successfully|Technical POC|[E2E Templates](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=list-of-templates)

## Step 5: BAU in GL

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.

|Tool|Activity|Description|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|---|
[GitLab](https://sgts.gitlab-dedicated.com/)|Set up GitLab dashboards|1. Configure Security dashboards|Technical POC|[Dashboards](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/dashboards)
|||2. Review DORA metrics|Technical POC|[Dashboards](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/dashboards)
||Monitor BAU in GitLab|A 2-week period to start and monitor activities in GitLab.|Technical POC|NA

### Performed by (roles)

|Performed by (roles)| Description|  
|---|---|
**All** |All Customers team members involved in the onboarding process
**Agency PM**| The Project Manager that acts on behalf of the Customer Agency (needs to be a public officer).
**Technical POC** |The Technical Point of Contact, typically someone with some management authority & the most technically competent member within the Customer Agency team (can be in-house or outsourced).

## What's next 

- [Onboard additional users in the SHIP-HATS portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/onboarding-users)
- [Create additional projects in the SHIP-HATS portal as needed](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-projects)
- [Add project tools or SHIP-HATS services via SHIP-HATS portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-tools)
- [Add applications/projects for project tools](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-applications)

## User roles and permissions

[User roles and permissions](user-roles-permissions.md ':include')