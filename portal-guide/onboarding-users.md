# Onboarding Users


<!--
This section describes the following:
- [Invite users](#invite-users)
- [Create Account](#create-account)
- [Approve new users](#approve-new-users)
-->


## [Invite users](#invite-users)
Subscription Admin (SA) and Project Admin (PA) can invite and add users to the subscription. Note that only SA can add a user as PA to their SHIP-HATS projects.

### To invite users

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](manage-account).

1. From the side menu, click **Users > Invite Users**. An invitation link is automatically generated.  
By default, a new invitation link has a 14 days expiry date.  Whenever you invite new users, the same link will be displayed with the remaining expiry date until it expires. In the example below, SA invites a new user to SHIP-HATS. As the invite was created 2 days earlier, the link is valid for the next 12 days.

   <kbd>![Invite Users](invite-users.png ':size=100%')</kbd>

1. Click **Email me** to send this link with the expiry date to your SHIP-HATS registered email address and forward it to the intended users so that they can provide required information in the **Invitation Form**.  
Alternatively, click the copy icon to copy and share the invite link with intended users. Note, in this case, make sure to inform the users about the expiry date of this link.

## [Create Account](#create-account)
You will receive an invitation email with a link to onboard to SHIP-HATS portal upon successful approval. 

Access the link via the onboarding email and perform the following steps based on the account that you want to create. 

### To create an account for a Public Officer

1. In the Invitation form, select the role as **Public Officer**. 

1. Enter the following details, and then click **Submit**.  

   - **First Name:** Enter first name of the user.
   - **Last Name:** Enter last name of the user.
   - **Public Service Email Address:** Enter official email address of the user.
   - **Require SEED Account:** Select this checkbox if the user requires a SEED account. This account is required only for a user who is actively involved in development work on a non-GSIB device. For more information, refer to the [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/) documentation.  
<br />

   <kbd>![Create Account](create-account.png ':size=100%')</kbd>

### To create an account for a Vendor:

1. In the Invitation form, select the role as **Vendor**.  

   <kbd>![Create Vendor Account](new-account-vendor.png ':size=60%')</kbd>
1. Enter the following details, and then click **Submit**.  

   - **First Name:** Enter first name of the user.
   - **Last Name:** Enter last name  of the user.
   - **Company Email Address:** Enter email address of the user. 
   - **Mobile Number:** Enter mobile number of the user.
   - **Organisation:** Enter organisation name of the user. 
   - **Department:** Enter department name of the user.
   - **Require SEED Account:** Select this checkbox if the user require a SEED account. This account is required only for users who are actively involved in development work on a non-GSIB device. For more information, refer to the [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/) documentation.  
<br />
   
   <kbd>![Create Account](create-vendor-account.png ':size=100%')</kbd>


## [Approve new users](#approve-new-users)
After a user submits the completed SHIP-HATS **Invitation Form**, Subscription Admin (SA) and Project Admin (PA) will be notified by an email to approve the user registration.

### To approve new user registration:
1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](manage-account).

   <kbd>![Pending User Approval Notification](pending_user_approval_notification.png ':size=100%')</kbd>

   If there is a pending user approval task for you, it will be displayed in the **ALERTS** section.  

2. Click **View** corresponding to that alert. You will be directed to the **Pending Approval** section.

   >**Tip:** Alternatively, from the side menu, click **Users** > **All Users**. 
   
   If there is a pending user approval task, the **Pending** section will display the number of users pending approval. Here, you can view the users that are pending your approval along with their email address.  

   <kbd>![Add User](tp-add-user.png ':size=100%')</kbd>   
    
   Only email addresses that are included in our approved list will be approved. If you provide an email address that is not included in our approved list, in the SHIP-HATS portal when approving the user, you will see a message indicating that this domain will be required to be included in TechPass. As required, you may select the **Proceed to whitelist domain** option to raise a service request. 
   
   <kbd>![Unapproved Domain](vendor-unapproved-user-domain.png ':size=100%')</kbd>

3. Click **Approve** corresponding to the user.

   <kbd>![Approve](tp-approve-user.png ':size=100%')</kbd>

4. In **Grant user access for:**, You can choose which tools to give access to. Following options are available:
   - **CI tools:** Select this option if the user is required to have access to JIRA, Confluence, Bitbucket, Bamboo, pCloudy, SonarQube, Fortify SCA & WebInspect, and Prisma Cloud services.
   - **SonaType tools:** Select this option if the user is required to have access to Nexus Repository and Nexus IQ Scan services.  

1. Click **Confirm**.  
This user is now approved as SHIP-HATS user under this account.

   >**Note:** Irrespective of agencies, individuals approved as SHIP-HATS users can be added to any SHIP-HATS project and will be billed under the account that initially approved them.  

## What's Next
- 

## Related Topics
- [Manage Users](manage-users)