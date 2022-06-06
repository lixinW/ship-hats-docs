# Access SHIP-HATS Portal

<!--
**Topics**
- [Prerequisites](#prerequisites)
- [Log In](#log-in)
- [Log in via TechPass](#log-in-via-techpass)
- [View Dashboard](#view-dashboard)
- [View User Profile](#view-user-profile)
- [Log Out](#log-out)
-->


## Prerequisites

- Before you start, you must have been [invited and onboarded to SHIP-HATS](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started-guide/#/onboarding-to-ship-hats?id=onboarding) by SHIP-HATS.
- Make sure that you have setup <span style="color:red">your OpenVPN connection</span>.

<span style="color:red">Will there be any prerequisites?
someone has to provide access, right permissions, etc.
set up and connect to openvpn?</span>.

## Log In

<!-- tabs:start -->

### **Log In**

**To log in to the SHIP-HATS portal**

1. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).
2. Click **Log In**.

    <kbd>![log-in](log-in.png ':size=100%')</kbd>

3. Enter your **Username**, **Password**, and then click **Login**.
    - If you are an SA or PA, the **Overview** page appears. For more details, refer to the [View dashboard](#view-dashboard) section.
    - If you are a regular user, the **Profile** page appears. For more details, refer to the [View user profile](#view-user-profile) section.

    <kbd>![dashboard](dashboard.png)</kbd>

<!--
<span style="color:red">explain the page and left nav briefly.</span>
-->

### **Log in via TechPass**

**To log in to the SHIP-HATS portal using TechPass**

1. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).
2. Click **Log In with TechPass**.

    <kbd>![log-in](tplogin.png ':size=100%')</kbd>

3. Enter your **Enter your TechPass details**, and then click **Next**.

    <kbd>![log-in](tp-sign-in.png ':size=100%')</kbd>

    You will be redirected to the GCC log-in page. 
1. Enter your TechPass email address along with the verification code from the Authenticator app and click sign in. 

    <kbd>![log-in](tp-gcc-log-in.png ':size=100%')</kbd>

5. Read through the **TechPass** Terms of Use, and then click **Accept**.

    <kbd>![log-in](tp-terms-of-use.png ':size=100%')</kbd>

6. Read through the **TechPass MDM** Terms of Use, and then click **Accept**.

    <kbd>![log-in](tp-mdm-terms-of-use.png ':size=100%')</kbd>

You have successfully linked your TechPass to SHIP-HATS. You can directly log in using TechPass for future access.  
<span style="color:red">Is there any step missing here?</span> 
- If you are an SA or PA, the **Overview** page appears. For more details, refer to the [View dashboard](#view-dashboard) section.
- If you are a regular user, the **Profile** page appears. For more details, refer to the [View user profile](#view-user-profile) section.

<!-- tabs:end -->


## View Dashboard
The **Overview** page of the subscription account gives the dashboard view of the subscription account. Only Subscription Admin (SA) and Project Admin (PA) can access this dashboard to view the following details:

- Subscription tier for the Billing Account. By default, you view the subscription details of the first account to which you were added as SA or PA. You can [switch account](manage-account), as needed.
- [Plan details](manage-accounts)
- Number of projects hosted on this account
- Number of users added to this account
- Projects using shared Bamboo agents and their usage quota 
- Announcements about SHIP-HATS services, maintenance notice, generic subscription updates, and any urgent or important messages
    <kbd>![Portal Announcements](portal-announcements.png ':size=60%')

>**Note:** The term **Overview** and **Dashboard view** may be used interchangeably.

<kbd>![overview](ship-update.png ':size=60%')</kbd>

## View User Profile

As a user (other than SA or PA), when you [log in](#log-in) to the [SHIP-HATS portal](https://www.ship.gov.sg/), you can complete the following actions:
- View your **Profile** page that includes information on your subscription, such as number of fortify and sonarqube applications tied to the subscription.

    <kbd>![Plan Details](plan-details.png ':size=100%')</kbd>
- Click the applications to view tokens and the expiry date. You can also download the information as CSV.

    <kbd>![Token Info](view-users-token.png ':size=100%')</kbd>
- View the user groups to which you belong.

    <kbd>![User Group](user-group-profile.png ':size=100%')</kbd>


## Log Out 
When you are done with your activities on the portal, you can log out as shown below.

### To log out from the SHIP-HATS portal
- Hover over your profile icon, and then click **Log out**.
    
    <kbd>![Log Out](log-out.png ':size=100%')</kbd>

- If you are inactive for five minutes on the portal, the system prompts you with the following message. Click **Yes, Keep me signed in** to continue your session.

    <kbd>![Idle Time Prompt After 5 Mins](idle-time-prompt-after-5-mins.png ':size=100%')</kbd>

- If you are inactive for 10 minutes on the portal, the system prompts you with the following message:

    <kbd>![Session Timed Out](session-timed-out.png ':size=100%')</kbd>

**Related Topics**
  - [Manage Account](manage-account)
  - [Manage Users](manage-users)
  - [Manage Projects](manage-projects)
  - [Manage Fortify applications](manage-fortify-applications)
  - [Declare DGP Systems](declare-dgp-systems)