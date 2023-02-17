# Onboard to SHIP-HATS

The following topic provides details for **onboarding to SHIP-HATS**. 

![Onboarding Flow](./images/onboarding-flow.png)

The above image provides high level steps to complete onboarding to SHIP-HATS. Detailed steps are provided below along with documentation links to complete the steps. 

## Step 0: Pre-onboarding

|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|
|---|---|---|
|Decide on base package + add-ons|[Agency PM](#performed-by-roles)|[Subscription](subscription)<br><br>[Tooling strategy](ship-hats-tools)
|Raise Internal AOR for 2.0 Tools & Services|[Agency PM](#performed-by-roles)|[Sample AOR (Accessible to Public Officers via intranet](https://go.gov.sg/sh2indicative)
|Raise Vendor SR (as applicable)|[Agency PM](#performed-by-roles)|NA|
|Sign up for [TechPass](https://portal.techpass.gov.sg/public/home)|[All](#performed-by-roles)|[Onboard to TechPass](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/onboard-public-officers-using-non-se-machines)

## Step 1: Subscribe to SHIP-HATS

?> Complete these steps in the **[TechBiz Portal](https://portal.techbiz.suite.gov.sg/)**. Public Officers can access **[how-to videos for subscription via TechBiz](https://sgdcs.sgnet.gov.sg/sites/IDA-GoSync/gdspdd-ai/ship/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FIDA-GoSync%2Fgdspdd-ai%2Fship%2FShared%20Documents%2FSHIP-HATS%202%2E0%2FOnboarding%20how-to%20videos)** via Intranet.


|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|
|Log in to the TechBiz portal|[Agency PM](#performed-by-roles)|[Log in to TechBiz portal](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/log-in-to-TechBiz-portal)
|Create Subscription Package|[Agency PM](#performed-by-roles)|[TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/techbiz-account)<br><br>|[Request for TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/request-for-techbiz-account)
|Approve Account|DD or above|[Approve or reject TechBiz account](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/approve-or-reject-techbiz-account)
|Create System Name|[Agency PM](#performed-by-roles)|[Manage TechBiz system](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/manage-techbiz-system)<br><br>[Create TechBiz system](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/create-techbiz-system)
|Add and configure products|[Agency PM](#performed-by-roles)|[Add and configure products](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/add-and-configure-products)
|Select the required Tool(s) and Add users|[Agency PM](#performed-by-roles)|[Manage user access for subscribed SGTS products](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/manage-user-access-subscribed-sgts-products)<br><br>You must subscribe to required Tools (e.g. GitLab) and add-ons as needed (e.g. Jira/Confluence), and then add users for each of the subscribed tools.

## Step 2: Onboard to SHIP-HATS

?> Complete these steps in the **[SHIP-HATS Portal](https://portal.ship.gov.sg/)**.


|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|
|Access SHIP-HATS Portal|[Agency PM](#performed-by-roles) & [Technical POC](#performed-by-roles)|[Access portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/access-ship-hats-portal)
|Verify Users and System (s)|[Agency PM](#performed-by-roles) & [Technical POC](#performed-by-roles)|[Manage users](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-users)
|Create project|[Agency PM](#performed-by-roles) & [Technical POC](#performed-by-roles)|[Manage projects](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-projects)
|Assign Project Admin|[Agency PM](#performed-by-roles) & [Technical POC](#performed-by-roles)|[Manage admins](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-admins)
|Add GitLab tool (and other tools as per your subscription)|[Technical POC](#performed-by-roles)|[Manage tools](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-tools)


## Step 3: Configure GitLab

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.

|Activity|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|
|Verify user mapping|[Technical POC](#performed-by-roles)|1. In SHIP-HATS Portal, click **GitLab group.** <br><br>2. In GitLab, Click **Subgroup information** > **Members**
|Set up SSH keys|Developer|[Communicate using SSH keys](communicate-using-ssh-keys)
|Set up GPG keys|Developer|[Sign commits with GPG](signing-commits-with-gpg)

## Step 4: Configure Pipelines

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.

|Activity|Description|[Performed by](#performed-by-roles)|GovTech Supporting Guide|  
|---|---|---|---|
|Set up Remote runners [Optional]<br><br>**Note:** You can complete this step in parallel with Configure CI Pipeline|If you are using Remote runners, you can connect to SHIP-HATS using:<br><br> **AWS VPC Endpoint** <br><br>or<br><br> **IPsec Tunnel**|[Technical POC](#performed-by-roles)|[Runners](runners)<br><br>[AWS VPC Endpoint](aws-vpc-endpoint)<br><br>or <br><br>[IPsec Tunnel](ipsec-tunnel)
|Configure CI pipeline|1. Copy the E2E template into your own repository and update the project variables|[Technical POC](#performed-by-roles)|[E2E Templates](pipeline-templates)
||2. Modify your pipeline using the Modular template [Optional]<br><br>This is an optional step. If the E2E template does not meet your requirement, you can modify your pipeline using the Modular templates for any additional capabilities.|[Technical POC](#performed-by-roles)|[Common Templates (Modular)](pipeline-templates)
||3. Apply Compliance Framework|[Technical POC](#performed-by-roles)|[Compliance Framework](compliance-framework)
|Configure CD pipeline <br>(non-production & production)| Execute deployment successfully on non-production and production|[Technical POC](#performed-by-roles)|[E2E Templates](pipeline-templates)

?> After you have completed above setup, you can use **[GitLab dashboards](dashboards)** and review **[DORA metrics](dashboards)** to ensure BAU in GitLab.


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


<!--

!> **Important:** SA can use the [TechBiz service to subscribe to SHIP-HATS](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/) to [onboard to the SHIP-HATS product](#onboarding-steps).


## Onboarding steps

To onboard or subscribe to SHIP-HATS, the [Subscription Administrator (SA)](#user-roles-and-permissions) must complete the following steps:

|Step|Task|Owner|
|---|---|---|
|1| Review and decide the [Subscription](subscription) required.|[Subscription Administrator (SA)](#user-roles-and-permissions)
|2 |Use the **[TechBiz service to subscribe to SHIP-HATS](https://docs.developer.tech.gov.sg/docs/techbiz-documentation/) to onboard to the SHIP-HATS product**.|  SA

## Post onboarding steps
After you have onboarded or subscribed to the SHIP-HATS product via the TechBiz service, complete the following steps:

|Step|Task|Owner|
|---|---|---|
|1|[Onboard to the SHIP-HATS Portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/onboarding-to-portal) <br><br>  If you are using an Internet device to onboard to the SHIP-HATS portal, your device must be [Onboarded to SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/) before SA can [Onboard to the SHIP-HATS Portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/onboarding-to-portal).|SA
|2|[Create a project](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-projects) |SA
|3|[Invite a Project Administrator (PA)](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-admins)|SA  
|4|[Provision GitLab](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-tools)|[Project Administrator (PA)](#user-roles-and-permissions)|
|5|[Log in to GitLab on your SEED device](https://docs.developer.tech.gov.sg/docs/ship-hats-tools/gitlab/gitlab-login)<br><br>SHIP-HATS 2.0 GitLab: https://sgts.gitlab-dedicated.com/ |PA|
|6|Navigate to your GitLab group  `https://sgts.gitlab-dedicated.com/WOG/<agencyname>/<groupname>`|PA|
|7|Verify GitLab Group created during TechBiz Subscription onboarding|PA|
|8|[Add SSH Key to securely communicate with GitLab](communicate-using-ssh-keys)|PA
|9|[Add a GPG (for signed commits) from your SEED Device](signing-commits-with-gpg)|PA
|9|Set up Environment Connectivity via [AWS VPC Endpoint](aws-vpc-endpoint) or [IPsec Tunnel](ipsec-tunnel) <br><br> This is an optional step.|PA|
|10|[Set up GitLab Runners](gitlab-runners) <br><br> This is an optional step.|PA
-->

<!--**Topics**
- [Prerequisites](#prerequisites)
- [Subscribing](#subscribing)
-->

<!--
## Prerequisites

- Make sure that you have the required [Subscription](subscription).
- A session is active for 20 minutes. Therefore, we recommend having the following details before clicking the onboarding link that you receive in your email: 
    |Information|Particulars Required|Notes|
    |---|---|---|
    |Details of the Primary and Secondary Subscription Admins|Name<br>Email<br>Mobile Number|For more information, refer to *User roles and permissions* content below.|
    |Details of the Billing contact|Name<br>Email<br>Contact Number<br>Address<br> Sub Business Unit code details|Sub Business Unit (SUB BU) is not your Department code. Please work with your finance team for the SUB BU code.|
    |Approval of the subscription by a MIC (Manager In-Charge).|The approver of the subscription has to be Deputy Director and above for signatory.|None|
    |Approver Details|Name<br>Email<br>Designation|None| 
- The onboarding link only lasts for 14 days. If you require an extension, send an email to [enquiries_ENP@tech.gov.sg](mailto:enquiries_ENP@tech.gov.sg).

## Subscribing 

The following image and table outlines the steps that you must complete to get started with SHIP-HATS. After you have completed these steps, you will need to perform additional steps to onboard to the SHIP-HATS portal and configure the tools that you want to use.  

These tasks may be completed by multiple people in your organization and SHIP-HATS team. However, these tasks must be completed in the specified order. All steps are required unless otherwise noted.
-->
<!--![Onboarding](./images/onboarding-ship-hats.png)-->
<!--
<p align="center">
  <img src="./images/subscribing-ship-hats.png">
</p>

|Step|Task|Owner|
|---|---|---|
|1|[Review the Subscription information](subscription).|Agency|
|2|Use your `gov.sg` email to send a request to [enquiries_ENP@tech.gov.sg](mailto:enquiries_ENP@tech.gov.sg) with the email address of your Primary Subscription Admin (SA).|Agency|
|3|Send onboarding link to the SA via email.|SHIP-HATS|
|4|Open the invitation link on an Internet device, enter the fields, and then submit the onboarding form.|Agency|
|5|Verify the information and send an email with the Memorandum of Understanding (MoU) to the approver nominated in the onboarding form.|SHIP-HATS|
|6|Reply `Approved` after receiving the email.|Agency Approver|
|7|SHIP-HATS Team provisions account for the Primary and Secondary SA.|SHIP-HATS |
|8|Send an email to SAs indicating that their account has been provisioned.|SHIP-HATS |
|9|[Onboard to TechPass](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/onboard-public-officers-using-non-se-machines).|Agency|
|10|[Onboard to SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/).|Agency|
|11|[Onboard to the SHIP-HATS Portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/onboarding-to-portal).| Subscription Admin (SA)|

-->



<!--
### What's Next
- [Complete the setup in the SHIP-HATS portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/onboarding-to-portal)
- [Invite Users via the SHIP-HATS Portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/manage-users?id=invite-users) 


### Related Topics
- [User roles and permissions](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/user-roles-and-permissions)-->

<!--

1. Use gov.sg email to send a request to [enquiries_ENP@tech.gov.sg](mailto:enquiries_ENP@tech.gov.sg) with the email address of your Primary Subscription Admin (SA).  
1. The SA receives the onboarding link via email.
1. Open the invitation link on an Internet device, enter the fields, and then submit the onboarding form. 
1. SHIP-HATS Team verifies the information. 
1. System will send an email with the Memorandum of Understanding (MoU) to the approver nominated in the onboarding form. 
1. Agency's approver is required to reply 'Approved’ after receiving the email. 
1. After approver replies, SHIP-HATS Team provisions the Primary SA and Secondary SA's account. 
1. SAs will receive an email to inform that your account is provisioned. 
1. SAs log into [SHIP-HATS Portal](http://ship.gov.sg) after their accounts have been provisioned and send the [invitation link](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-users?id=invite-users) to their users for them to self-create accounts and approve the user accounts.
-->

