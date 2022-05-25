# Support

## Raise a Service Request

- [Create a Service Request](https://jira.ship.gov.sg/servicedesk/customer/portal/11)

## Maintenance Timing


| Tool | Frequency/Timing | Impact to activity during this timing |
| --- | --- | --- |
| RDS: </br>Bitbucket</br>Bamboo</br>Jira</br>Confluence</br>Crowd </br>Gitlab | Daily, 2am to 3am |Database commits may fail. |
| NFS Snapshots: </br>Bitbucket </br>JIRA </br>Confluence </br>Crowd | Daily, 3am to 4am |New activity happening after the snapshot is initiated may not be included in snapshot. |
| EBS Snapshots:</br> Nexus Repo </br>Nexus IQ </br>Bamboo </br>LDAP </br>Gitlab | Daily, 3am to 4am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| NFS Backup to EBS | Daily, 4am to 5am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| S3 Bucket Snapshots: </br> Nexus Repo | Daily, 3am to 6am | Nexus Repo will be frozen while this is ongoing. (Read-only) |


## Maintenance Releases

Below are all the details on SHIP-HATS releases.

### 2022 Releases

| Release Number | Release Details | Release Date |
| :------- | :------- | :------- |
| 3.14.14 | SHIP Monthly Maintenance<br><ul><li>Security Patching and Update:</li><ul><li>Bitbucket</li><li>Confluence</li><li>Crowd</li><li>Jira/GDSJira</li><li>Synchrony</li><li>Digital AI</li></ul><li>Version Upgrade:</li><ul><li>Bamboo ver 8.0.6</li><li>Nexus Repo ver 3.38.0</li><li>Nexus IQ ver 135</li></ul> | 26 Mar 2022 |
| 3.13.14 | <ul><li>Security Patching for the following tools:</li><ul><li>Crowd</li><li>Bitbucket</li><li>Bamboo</li><li>Jira/GDSJira</li><li>Confluence</li><li>Nexus IQ</li><li>Nexus Repo</li></ul> | 26 Feb 2022 |
| 3.13.13 | **Portal new features/enhancements** </br><ul><li>Features to specify project key or remove projects on:</li><ul><li>Jira</li><li>Confluence</li><li>Bitbucket</li></ul><li>Login page enhancement</li></ul>Version upgrade</br><ul><li>Thinking HATS ver 2.12.0 </ul> | 25 Feb 2022 |
| 3.12.12 | <ul><li>Security patching/version upgrade</li><ul><li>Patching for the following tools:</li><ul><li>ulNetapp patching; removal of log4j binary </li><li>Nginx patching</li><ul><li>Endpoints</li></ul><li>XL Release & Deploy patching</li><li>Crowd patching</li><li>Bamboo patching<ul><li>include Catalina out to beat config</li></ul><li>Jira_patching</li><li>Confluence patching</li><li>Gitlab patching</li></ul><li>Version Upgrade for following tools:</li><ul><li>Bitbucket version upgrade 7.17.4</li><li>Nexus Repo version upgrade 3.37.3</li><li>Nexus IQ version upgrade 131</li></ul>  | 29 Jan 2022|
  | 3.12.11 | **SHIP** </br><ul><li>TechPass integration enablement</li><ul><li>Bamboo</li><li>Bitbucket</li><li>Confluence</li><li>Jira/GDSJira</li><li>Nexus Repo and IQ</li></ul>**SHIP-HATS PORTAL** </br><ul><li>TechPass integration enablement</li></ul>**HATS** </br> <ul><li>Thinking Hats v2.11.0</li><li>Hats Onboarding v1.14.0</li><li>SSC Roles v1.14.0</li><li>TechPass integration enablement</li><ul><li>Fortify</li><li>SonarQube</li></ul> | 22 Jan 2022 |

### Previous Releases
  
| Release Number | Release Details | Release Date |
| :------- | :------- | :------- |
| 1.0.0	| <ul><li>SHIP GA (General Availability), comprises the following:</li><ul><li>Common Development Stack</li><li>Standard Build Management and Test Tools</li><li>SHIP Portal (MVP)</li> | 31 May 2020 |
| 2.0.0	| <ul><li>SHIP Release Management Launch</li><ul><li>Release Management to GCC AWS </li><li>Enhanced HATS Testing Tools</li>| 08 Oct 2020 |
| 2.1.0	| <ul><li>S	SHIP Public Code Repository (aka Public Gitlab)</li>| 09 Dec 2020 |
| 3.0.0	| <ul><li>SHIP Release Management to GCC Azure (CD) </li> |	22 Feb 2021 |
| 3.0.1	| <ul><li>Bamboo version upgrade to 7.2.2	</li> | 27 Feb 2021 |
| 3.1.1	| <ul><li>SHIP-HATS Service Portal, with following new features:</li><ul><li>RSubscription Summary</li><li>Quota management</li><li>Creation of new project, application</li><li>Management of team members</li><li>Automated onboarding workflow</li><li>(Above features will be rolled out progressively to users once migrated. First batch of users to be migrated are GDS users; remaining users to be migrated in subsequent batch planned end of March)</ul><br><ul>HATS new testing tools</li><li>Container Scanner (Prisma Cloud, formerly Twistlock) to automatically scan container images via the CI Pipeline against known vulnerability</li><li>Device Test Farm (Mobile automation)</li><li>Accessibility Testing (AXE)</li> | 12 Mar 2021 |