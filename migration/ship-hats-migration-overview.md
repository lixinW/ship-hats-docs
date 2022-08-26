# SHIP-HATS Migration Overview

We are upgrading to SHIP-HATS 2.0. **SHIP-HATS 2.0 will be running on GitLab**, offering a seamless experience for Agencies to implement an end-to-end SaaS-based CI/CD solution.
<!--
**Topics**
- [Change Summary](#change-summary)
- [Why this Change is Essential](#why-this-change-is-essential)
- [Key Benefits](#key-benefits)
-->
## Change Summary

<!--![Tools](tools.png)-->

|Tools in 1.0|Tools in 2.0|
|---|---|
|Thinking HATS|Gitlab Security Dashboard<br>-or-<br>Thinking HATS	
|Jira|Gitlab Issues<br>-or-<br>Jira (Cloud)|
|Confluence|GitLab Wiki<br>-or-<br>Confluence (Cloud)|
|Bitbucket|GitLab|
|Bamboo|GitLab|
|Fortify Static Code Analyzer|GitLab SAST<br>-or-<br>Fortify On Demand (FOD) SAST|
|SonarQube Community/Developer Edition|GitLab Code Quality <br>-or-<br>SonarQube Community/Developer Edition|
|Nexus IQ Server| GitLab Dependency Scanning<br>-or-<br>Nexus IQ Server
|Prisma Cloud|GitLab Container Scanning<br>-or-<br>Prisma Cloud|
|Fortify WebInspect Enterprise|GitLab DAST<br>-or-<br>Fortify On Demand (FOD) DAST|
|pCloudy |pCloudy |
|Purple HATS|GitLab (Pa11y)<br>-or-<br>Purple HATS
|Digital.ai|GitLab|
|Nexus Repository Pro|GitLab Package Registry <br>-or-<br>Nexus Repository Pro

<!--
| **Tools** | **Change** |
| --- | --- |
| <ul><li>Bitbucket</li><li>Bamboo</li><li>Digital.ai</li></ul> | <br><br><br>GitLab |  
| <ul><li>Fortify SCA</li><li>WebInspect</li></ul> | <br><br>SaaS-based Fortify on-demand |  
|<ul><li>Jira </li><li>Confluence </li></ul>|<br><br>SaaS-based Jira & Confluence|
| <ul><li>Nexus IQ </li><li>Nexus Repository Pro </li><li>pCloudy Test Farm </li><li>SonarQube </li><li>Prisma Cloud </li></ul> | <br><br><br><br><br>No change |  
-->
### Pipeline Definition Format

CI/CD pipeline in SHIP-HATS 2.0 uses [YAML](https://en.wikipedia.org/wiki/YAML) for configuration. 

## Why this Change is Essential
Atlassian is sunsetting the support for self-hosted Bitbucket and Bamboo. Therefore, we must replace these tools.  

We are taking the opportunity to move to GitLab (a SaaS model) that enables you to enjoy the benefits of a more progressive CI/CD product with value-added features. Moving from self-hosted COTS to GitLab also enables us to focus our engineering efforts on supporting you with more comprehensive CI/CD templates and other resources to help you get started faster.

## Key Benefits

- **A modernized and updated CI/CD platform:** Stronger integration of CI and CD tools making it easier for agencies to adopt CD using GitLab 
- **Ease of compliance:** Automated DevSecOps capabilities and pipeline-as-a-code to comply with the new DevSecOps Policy easily 
- **Performance Management Dashboard:** Value-Stream Measurement capabilities that allow Agencies to capture key industry metrics, such as lead time to deployment and deployment frequency, to monitor the effectiveness of their DevSecOps practices 
- **Ease of access:** Secure and VPN-less access to the SHIP-HATS 2.0 platform  

?> **Note:** The benefits will be rolled out in phases.

<!--
## Features

- Saas with in-country hosting
- Progressive and timely product roadmap and support
- Ease of compliance
- Dashboarding Capabilities for DORA Metrics and Security Findings
- One-time migration


-->