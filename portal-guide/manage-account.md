# Manage Account

As a SHIP-HATS a Subscription Admin (SA) or a Project Admin(PA), you can manage your account and complete the following tasks.

- [Switch account](#switch-account)
- [Update admin profile](#update-admin-profile)
- [Update user profile](#update-user-profile)
- [Reset 2FA](#reset-2fa)
- [View plan details](#view-plan-details)
- [View billing information](#view-billing-information)
- [Off-board an account](#off-board-an-account)

## [Switch account](#switch-account)
If you are a SA or PA for more than one subscription account in SHIP-HATS, you may need to switch between these accounts to Manage users, Manage Projects, Viewing Plan Details and Viewing Billing Info.

### To switch account:

1. From the [**Overview**](#view-dashboard) page, hover over **Billing Account** at the upper-right area of the page and choose **Switch account**.

    <kbd>![switch-account](switch-account.png ':size=100%')</kbd>

2. Choose the required billing account to view its dashboard.

    <kbd>![switch-account](switch-account-choose-account.png ':size=100%')</kbd>

## [Update admin profile](#update-admin-profile)
SA and PA can update their profile from the [**Overview**](#view-dashboard) page.

### To view and update profile as SA and PA:

1. From the [**Overview**](#view-dashboard) page, hover over your profile icon at the upper-right corner. Your user name and user role for this account are displayed. In the below example, the logged in user is a **Subscription Admin** for this account.

    <kbd>![view-and-update-profile-user-role-and-name-blurred](view-and-update-profile-user-role-and-name-blurred.png ':size=75%')</kbd>

2. Choose **View Profile**. Your personal information and details of accounts in which you are SA and PA are listed.
3. To update your **Personal Information**, click the edit icon.

    <kbd>![edit-profile-details-blurred](edit-profile-details-blurred.png ':size=75%')</kbd>


## [Reset 2FA](#reset-2fa)
You can reset your 2FA for SHIP-HATS anytime by following the below steps.

### To reset 2FA for SHIP-HATS:

1. Disconnect from your **OpenVPN Connect** client.
2. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).

    <kbd>![reset-pwd-login-page-1](reset-pwd-login-page-1.png ':size=75%')</kbd>

3. Click the link indicated in the above image to reset your password. You will be directed to the **Self-help Requests** page.

    <kbd>![reset-2fa-self-help-page](reset-2fa-self-help-page.png ':size=75%')</kbd>

4. Click **Reset 2FA**.
5. Enter your **Username** used for** registering with SHIP-HATS.
6. Select the checkbox to confirm that you are not a robot and click **Submit**.

    <kbd>![2fa-reset-request-success](2fa-reset-request-success.png ':size=75%')</kbd>

You will receive a notification stating that your SHIP-HATS 2FA has been reset and with instructions to be followed by you.

## [View plan details](#view-plan-details)

SA and PA can view the plan details of their subscription account(s) from the dashboard view.

### To view plan details of a subscription:

1. Ensure you are in the required account. If needed, refer to [Switching account](#switch-account).

    <kbd>![plan-details](plan-details.png ':size=100%')</kbd>

2. From the [**Overview**](#view-dashboard) page, hover over **Billing Account** at the upper-right area of the page and choose **Plan Details**.

    <kbd>![plan-details](plan-details-1.png ':size=50%')</kbd>

Alternatively, click **Plan details** from **Overview** as shown below.

>**Note:** SHIP-HATS users other than SA and PA can view their associated subscription account details, such as **Billing Account Name** and **Billing Account Number**, from their **Profile** page as shown below. Refer to [View user profile](#view-user-profile) and [Update user profile](#update-user-profile) for additional information.
><kbd>![view-subscription-details-for-other-users](view-subscription-details-for-other-users.png ':size=75%')</kbd>

## [View billing information](#view-billing-information)

If you are a Subscription Admin, you will be able to view and edit the billing information of their subscription account(s).

### To view and edit billing information:

1. Ensure you are in the required account. If needed, refer to [Switching account](#switch-account).
2. From the [**Overview**](#view-dashboard) page, hover over **Billing Account** at the upper-right area of the page, and then choose **Billing Info**.

    <kbd>![billing-info-menu](billing-info-menu.png ':size=75%')</kbd>

This page has three sections: Billing Information, Approver Information and Signed Service Sheets (SS).

**Billing Information**

<kbd>![billing-information](billing-information.png ':size=75%')</kbd>

SA can edit all the details in this section except **Billing Agency**.

>**Note:** GL Account is applicable for Govtech agencies and Sub-Business Unit is applicable for non-Govtech agencies.

**Approver Information**

You can find the approver details for this account.

<kbd>![approver-information](approver-information.png ':size=75%')</kbd>

**Signed Service Sheets(SS)**

You can find the signed service sheets for this account.

<kbd>![signed-service-sheet](signed-ss.png ':size=75%')</kbd>


## Off-board an Account

If you are a Subscription Admin (SA), you can off-board your subscription account after the trial period has lapsed or project is coming to an end. 

### Prerequisites
- Take backup of your data.
- Plan to complete the steps at least one week before the off-boarding date.
- Inform your users that they will not have access to tools after the off-boarding date.


### To off-board an account:

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/). 
1. Select an expected date to off-board. 

    - For a subscribed account, there is a minimum commitment of 6 months stated in the service sheet. Therefore, you will be allowed to select a date after fulfilling the 6 month period only.
    - If you are on a trial account, you can select a date of your choice to off-board the account.
1. After you have a confirmed date, create a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) with following details:  

    - In the **Title** field, add the title in the following format: *[REQUEST TO OFF-BOARD] AgencyName - BillingRef - SubscriptionTitle*
    - In the **Description** field, provide the following details: 
        - Expected date to off-board
        - Users list (including SA & PA)
        - Project title & project key for Jira/Confluence/BB/Bamboo
        - Fortify app name
        - SonarQube app name
        - PrismaCloud app name
        - Text box to capture Sonatype app name
        - Master billing crowd/ldap group name  

    You will receive an email confirmation with further details. 

**After you have raised the service request for off-boarding:**
- When SA or PA logs in to the SHIP-HATS portal, in the **Alerts** section, you will see a termination message.
- Tools cannot be added
- Changing the PA function is disabled. 
- User invitations are disabled. 
- After the termination date, SA or PA will not be able to view the subscription details for the off-boarded account. However, if SA or PA have other subscription accounts, theu will continue to view details for these additional subscriptions accounts.
