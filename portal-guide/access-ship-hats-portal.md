# Access SHIP-HATS Portal

**Topics**
- [Log In](#log-in)
- [Log in via TechPass](#log-in-via-techpass)
- [View Dashboard](#view-dashboard)
- [View User Profile](#view-user-profile)
- [Log Out](#log-out)


## Log In

### Prerequisites

- Before you start, you must have been invited and onboarded to SHIP-HATS.
- Once you have successfully onboarded, make sure that you have setup your OpenVPN connection.

Will there be any prerequisites?
someone has to provide access, right permissions, etc.
set up and connect to openvpn?

After the above are successfully completed, you can proceed to log in to SHIP-HATS. 


### To log in to the SHIP-HATS portal:

1. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).
2. Click **Log In**.

    <kbd>![log-in](log-in.png ':size=100%')</kbd>

3. Enter your **Username** ,**Password** and click **Log In**.

    - If you are an SA or PA, the **Overview** page appears. For more details, refer to the [View dashboard](#view-dashboard) section.
    - If you are a regular user, the **Profile** page appears. For more details, refer to the [View user profile](#view-user-profile) section.

Add result statment and image of landing page (dashboard page?)

<kbd>![dashboard]()</kbd>

explain the page and left nav briefly.


## Log in via TechPass

### To log in to the SHIP-HATS portal using TechPass:

1. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).
2. Click **Log In with TechPass**.

    <kbd>![log-in](tplogin.png ':size=100%')</kbd>

3. Enter your **Enter your TechPass details** and click **Next**.

    <kbd>![log-in](tp2.png ':size=100%')</kbd>

4. You will be redirected to the GCC log-in page. Enter your TechPass email address along with the verification code from the Authenticator app and click sign in. 

    <kbd>![log-in](tpgcc1.png ':size=100%')</kbd>

5. Read through the **TechPass** Terms of Use and click **Accept**.

    <kbd>![log-in](tptou.png ':size=100%')</kbd>

6. Read through the **TechPass MDM** Terms of Use and click **Accept**.

    <kbd>![log-in](techpassmdm.png ':size=100%')</kbd>

You have successfully linked your TechPass to SHIP-HATS. You can directly log in using TechPass for future access. 


## View Dashboard
The **Overview** page of the subscription account gives the dashboard view of the subscription account. Only Subscription Admin (SA) and Project Admin (PA) can access this dashboard to view the following details:

- Subscription tier for the Billing Account
- [Plan details](#view-plan-details)
- Count of projects hosted on this account
- Count of users added to this account
- Projects using shared Bamboo agents and their usage quota. 
- Announcements about SHIP-HATS services, maintenance notice, generic subscription updates, and any urgent or important messages.
    <kbd>![Portal Announcements](portal-announcements.png ':size=60%')

>**Note:** The term **Overview** and **Dashboard view** may be used interchangeably.

<kbd>![overview](ship-update.png ':size=100%')</kbd>

>**Notes:**
>- If you are an SA or PA for a subscription account, when you log in, by default, you will be viewing the subscription details of the first account to which you were added as SA or PA. If you want to switch to a different subscription account, refer to [**Switch Account**](#switch-account).
>- SA and PA must have logged in to SonarQube at least once before proceeding to create applications in SonarQube. Though only SA and PA can create applications in SonarQube, we recommend all users to log in to SonarQube at least once to ease the process if a user role is changed to a PA role in the future. Refer to [SHIP-HATS integrated tools version](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/ship-hats-integrated-tools-version) for SonarQube's URL.

## View User Profile
When users other than SA or PA log in to the [SHIP-HATS portal](https://www.ship.gov.sg/), they are directed to their **Profile** page. You may view more information on your subscription ie. the number of fortify and sonarqube applications tied to the subscription.

<kbd>![profile-of-other-users](info.png ':size=100%')</kbd>

Users can click on the applications to view tokens and the expiry date. The information is also downloadable as CSV

<kbd>![token info](fa.png ':size=100%')</kbd>

Users are also able to view the user groups they belong to.

<kbd>![user group](profile-2.png ':size=100%')</kbd>


## Log Out 
When you are done with your activities on the portal, you can log out as shown below.

### To log out from the SHIP-HATS portal:
- Hover over your profile icon, and then click **Log out**.
    
    <kbd>![log-out](log-out.png ':size=100%')</kbd>

If you are inactive for five minutes on the portal, the system prompts you with the following message. Click **Yes, Keep me signed in** to continue your session.

<kbd>![idle-time-prompt-after-5-mins](idle-time-prompt-after-5-mins.png ':size=100%')</kbd>

If you are inactive for 10 minutes on the portal, the system prompts you with the following message.

<kbd>![session-timed-out](session-timed-out.png ':size=100%')</kbd>




**Related Topics**
  - [Manage Account](manage-account)
  - [Manage Users](manage-users)
  - [Manage Projects](manage-projects)
  - [Manage Fortify applications](manage-fortify-applications)
  - [Declaring DGP Systems](declaring-dgp-systems)