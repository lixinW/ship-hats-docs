# Manage applications

**Topics**

- [Add applications to a project tool](#add-applications-to-a-project-tool)
- [Remove applications from a project tool](#remove-applications-from-a-project-tool)


## Add applications to a project tool

By default, when you add a project tool, an application is added. However, you can add additional applications to the following tools:
- Prisma Cloud
- Fortify On-Prem
- Fortify on Demand
- Nexus IQ
- SonarQube - Community Edition
- SonarQube - Developer Edition


### To add an application to a project tool
1. Go to **Projects** > **All Projects**.

    <kbd>![All Projects](./images/portal-projects-all-projects.png)</kbd>

1. Navigate to your project, and then click **Manage**.
1. Go to the required tab, and then click **Add another** under the project tool to which you want to add another application.  
    The **Add new tool** window appears. 
1. Provide values in the available fields, and then click **Add**.    
    The new application is added.


## Remove applications from a project tool

You can remove app from the following project tools:
- Confluence
- Container Image Scanner
- Fortify SCA & WebInspect
- Jira
- Nexus IQ
- SonarQube

### To remove an app

1. Go to **Projects** > **All Projects**.
1. Navigate to your project, and then click **Manage**.
1. On the tool, click **Manage**.  
    The **Manage Tool** window appears.
1. From the dropdown, select **Remove App**. 
    **Select App to Remove:** appears, displaying a list of apps. 

    ![removetool](./images/removetool.png)

1. Next to the app that want to remove, click **Remove**.  
    The **Remove** window appears.

    ![remove](./images/confirmremove.png)
1. Enter the requested information, and then click **Proceed**.  

    ![proceed](./images/proceed.png)
    The selected app is removed. If this the last app for the tool, the project tool is also removed. 
