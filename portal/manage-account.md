# Manage Account

**Topics**
- [Switch account](#switch-account)
- [View plan details](#view-plan-details)
- [View billing information](#view-billing-information)
- [Modify billing information](#modify-billing-information)
- [Update admin profile](#update-admin-profile)
- [Off-board an account](#off-board-an-account)

## Switch account
If you are a SA or PA for more than one subscription account in SHIP-HATS, you may need to switch between these accounts to Manage users, Manage Projects, Viewing Plan Details and Viewing Billing Info.

### To switch account

1. From the **[Overview](access-ship-hats-portal)** page, hover over **Billing Account** at the upper-right area of the page and choose **Switch account**.

    <kbd>![switch-account](./images/switch-account.png ':size=100%')</kbd>

1. Choose the required billing account to view its dashboard.

    <kbd>![switch-account](./images/switch-account-choose-account.png ':size=100%')</kbd>



## View plan details

SA and PA can view the plan details of their subscription account(s) from the dashboard view.

### To view plan details of a subscription

1. Ensure you are in the required account. If needed, refer to [Switch account](#switch-account).

    <kbd>![plan-details](./images/plan-details.png ':size=100%')</kbd>

1. From the **[Overview](access-ship-hats-portal)** page, hover over **Billing Account** at the upper-right area of the page and choose **Plan Details**.

    <kbd>![plan-details](./images/plan-details-1.png ':size=50%')</kbd>

    Alternatively, click **Plan details** from **Overview** as shown below.

    >**Note:** SHIP-HATS users other than SA and PA can view their associated subscription account details, such as **Billing Account Name** and **Billing Account Number**, from their **Profile** page as shown below. Refer to [Access user profile](#view-user-profile) and [Update user profile](users-self-help) for additional information.
    >
    ><kbd>![View Subscription Details](./images/view-subscription-details-for-other-users.png ':size=75%')</kbd>

## View billing information

If you are a Subscription Admin, you will be able to view the billing information of their subscription account(s).

### To view the billing information

1. Ensure you are in the required account. If needed, refer to [Switch account](#switch-account).
2. From the **[Overview](access-ship-hats-portal)** page, hover over **Billing Account** at the upper-right area of the page, and then choose **Billing Info**.

    <kbd>![billing-info-menu](./images/billing-info-menu.png ':size=75%')</kbd>

    You can view information in the following three sections: Billing Information, Approver Information, and Signed Service Sheets (SS).

    - **Billing Information**

        <kbd>![billing-information](./images/billing-information.png ':size=75%')</kbd>

        >**Note:** GL Account is applicable for GovTech agencies and Sub-Business Unit is applicable for non-GovTech agencies.

    - **Approver Information**

        You can find the approver details for this account.

        <kbd>![approver-information](./images/approver-information.png ':size=75%')</kbd>

    - **Signed Service Sheets(SS)**

        You can find the signed service sheets for this account.

        <kbd>![signed-service-sheet](./images/signed-ss.png ':size=75%')</kbd>

## Modify billing information
If you are a Subscription Admin, you will be able to modify the billing information of their subscription account(s).

### To view the billing information

1. Ensure you are in the required account. If needed, refer to [Switch account](#switch-account).
2. From the **[Overview](access-ship-hats-portal)** page, hover over **Billing Account** at the upper-right area of the page, and then choose **Billing Info**.

    <kbd>![billing-info-menu](./images/billing-info-menu.png ':size=75%')</kbd>

    You can view information in the following three sections: Billing Information, Approver Information, and Signed Service Sheets (SS).

    - **Billing Information**

        <kbd>![billing-information](./images/billing-information.png ':size=75%')</kbd>

        SA can edit all the details in this section except **Billing Agency**.

        >**Note:** GL Account is applicable for Govtech agencies and Sub-Business Unit is applicable for non-Govtech agencies.

    - **Approver Information**

        You can find the approver details for this account.

        <kbd>![approver-information](./images/approver-information.png ':size=75%')</kbd>

    - **Signed Service Sheets(SS)**

        You can find the signed service sheets for this account.

        <kbd>![signed-service-sheet](./images/signed-ss.png ':size=75%')</kbd>

## Update admin profile
SA and PA can update their profile from the **[Overview](access-ship-hats-portal)** page.

### To view and update profile as SA and PA

1. From the **[Overview](access-ship-hats-portal)** page, hover over your profile icon at the upper-right corner. Your user name and user role for this account are displayed. In the below example, the logged in user is a **Subscription Admin** for this account.

    <kbd>![view-and-update-profile-user-role-and-name-blurred](./images/view-and-update-profile-user-role-and-name-blurred.png ':size=75%')</kbd>

1. Choose **View Profile**. Your personal information and details of accounts in which you are SA and PA are listed.
1. To update your **Personal Information**, click the edit icon.

    <kbd>![edit-profile-details-blurred](./images/edit-profile-details-blurred.png ':size=75%')</kbd>


## Off-board an Account

If you are a Subscription Admin (SA), you can off-board your subscription account after the trial period has lapsed or project is coming to an end. 

### Prerequisites
- Take backup of your data.
- Plan to complete the steps at least one week before the off-boarding date.
- Inform your users that they will not have access to tools after the off-boarding date.


### To off-board an account

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