# Manage tools and applications

**Topics**

- [Add project tools](#add-project-tools)
- [Create project tool with customised project key](#create-project-tool-with-customised-project-key)
- [Remove project tools](#remove-project-tools)


## Add project tools

SA or PA can add the required project tools as explained below. You can add tools under the **Subscribed Tools** section based on the tools quota allotted for your subscription type. 


### To add project tools

1. From the side menu, click **Projects** > **All Projects** to view all the projects in this subscription account. If needed, refer to [Switch account](manage-account).
1. Locate the project to which you want to add a tool, and then click the project.
    > **Note:** Alternately, click three dots for more options, and then click **Manage Project**.
1. Locate the tool that you want to add, click **Create**, and follow the specific steps in table for the tool that you want to add.

    |Available Tools|Steps|
    |---|---|
    |GitLab|Make sure that at least 1 Project Admin has a GitLab account and is added to the TechPass group.<ol><li>Click the **Tool Type** > **Select Tool** drop-down list, and select **GitLab**.</li><li>In the **GitLab Group Name**, enter the group name.</li> <ol> |
    |Jira|<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list, and select **Jira**.</li><ol>|
    |Confluence|<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list, and select **Confluence**.</li><ol>|
    |Nexus IQ|<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list.</li><li> Enter values in the **Application Name** and **Application ID** fields.</li><ol>|
    |Nexus Repo|<ol><li>Click **Add**.</li><li>Submit a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11/) to add this tool.</li><ol>|
    |pCloudy|<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list, and select **pCloudy Device Farm & HATS Browser Farm**.</li><ol>|
    |Prisma Cloud|<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list, and then select **Container Image Scanner**.</li><li>In the **Scanner type** field, select **Prisma Cloud**</li><li>In the **App Name** field, enter the required value. </li><ol>|
    |SonarQube - Community Edition|Make sure that you have logged in to [SonarQube](https://sonar.hats.stack.gov.sg/sonar) at least once.<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list.</li><li>In the **App Name** field, enter the required value.</li><ol>|
    |SonarQube - Developer Edition|Make sure that you have logged in to [SonarQube](https://sonar1.hats.stack.gov.sg/sonar) at least once.<ol><li>Click **Add**.</li><li>Click the **Select Tool** drop-down list.</li><li>In the **App Name** field, enter the required value.</li><ol>|
    |Fortify on Demand| <ol><li>Click the **Select Tool** drop-down list.</li><li> Provide values in the **App Name** field.</li><ol>|

    >**Note:** After you reach the quota, the respective tool name(s) will be disabled in the **Select Tool** drop-down list. If you still want to add these tools, send an email to [enquiries_ENP@tech.gov.sg](enquiries_ENP@tech.gov.sg).    
1. Click **Add**.   
    
    The selected project tool and application is added.


## Create project tool with customised project key
Subscription Admin (SA) and Project Admin (PA) can customise the project keys when adding app tools on SHIP-HATS. This is currently applicable for Jira and Confluence.  

### To customise project key 

1. Go to **Projects** > **All Projects**.
1. Identify your project, and then click the project.
    > **Note:** Alternately, click three dots for more options, and then click **Manage Project**.

1. Locate the tool that you want to add, click **Create** > **Add** > **Customise Project Key**. 
<!--
1. Choose the required tool.

    ![Add new Development tool](./images/add-new-dev-tool.png)

1.  Select **Customise Project Key**.

    ![customise](./images/customise.png)
-->

1. In the **Project Key** field, enter the required project key. A project key can include 2-10 characters, consisting of uppercase letters A-Z and numbers from 0-9. First character must be an alphabet. 
<!--    ![add](./images/addnewkey.png)-->

1. Click **Add**. 



## Add applications to a project tool

By default, when you add a project tool, an application is added. However, you can add additional applications to the following tools:
- Prisma Cloud
- Fortify on Demand
- Nexus IQ
- SonarQube - Community Edition
- SonarQube - Developer Edition
<!--- Fortify On-Prem-->


### To add an application to a project tool



1. From the side menu, click **Projects** > **All Projects** to view all the projects in this subscription account. If needed, refer to [Switch account](manage-account).
1. Locate the project to which you want to add an application to a project tool, and then click the project.
    > **Note:** Alternately, click three dots for more options, and then click **Manage Project**.
1. Click the tool to which you want to add an application, and then click **Add another**.  
    The **Add new tool** window appears. 
1. Provide values in the available fields, and then click **Add**.    
    The new application is added.


