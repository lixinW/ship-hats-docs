# Tools

The following section provides list of tools for each stage in CI/CD pipeline offered under **SHIP-HATS**. 

|Stage|GitLab Native|Alternative Tool|
|---|---|---|
|Access|TechPass & SEED|TechPass & SEED|
|Plan|GitLab Issues|Jira 	
|Plan|GitLab Wiki| Confluence 
|Plan|Gitlab Security Dashboard|N/A|	
|Build|GitLab CI/CD|N/A|
|Build|GitLab Package Registry|Nexus Repository Pro|
|Build|GitLab Dependency Scanning|Nexus Intelligence/Nexus IQ Server|
|Build Testing |GitLab SAST |Fortify-on-Demand SAST
|Build Testing|[XCA (available for all by default)](#extended-code-analysis) |[XCA (available for all by default)](#extended-code-analysis) 
|Other Tests|GitLab Code Quality Scanning Tool <br> <br>**Note:** Please refer to [our recommendation and assessment](#gitlab-vs-sonarqube) below before choosing GitLab Code Quality Scanning Tool. |SonarQube Community/Developer Edition
|Other Tests|GitLab DAST|Fortify-on-demand DAST
|Other Tests|GitLab Container Scanning|N/A
|Other Tests|N/A|pCloudy Test Farm
|Other Tests|GitLab (Pa11y)|Purple HATS
|Deploy & Release|GitLab CI/CD|N/A|

?> **SHIP-HATS tools** such as GitLab, Confluence, Jira, Nexus Repo, Nexus IQ, and SHIP-HATS Service Desk **can be accessed via GSIB**.

## Tooling Strategy

[Tooling strategy](./snippets/tooling-strategy.md ':include')

## Extended Code Analysis

[XCA](./snippets/extended-code-analysis.md ':include')

## Key Tool Decommission Dates

Refer to [**Key tool decommission dates**](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=key-tool-decommission-dates).

## Tools Change Summary

Refer to [**Change Summary**](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-overview?id=change-summary).

<!--

|Stage|GitLab Native|Alternative Tool|
|---|---|---|
|Access|TechPass & SEED|TechPass & SEED|
|Plan|GitLab Issues/Wiki|Jira Cloud, Confluence Cloud (new!)
|Build|GitLab CI/CD<br><br>GitLab Package Registry<br><br>GitLab Dependency Scanning|NA<br><br>Nexus Repo<br><br>Nexus Intelligence|
|Build Testing|GitLab SAST|Fortify-on-Demand (new!)
|Other Tests|GitLab Code Quality Scanning Tool <br><br>GitLab DAST<br><br>GitLab Container Scanning<br><br>NA|SonarQube Developer Edition (On-Prem)<br><br>Fortify-on-demand (new!)<br><br>NA<br><br>pCloudy Test Farm
|Deploy & Release|GitLab CI/CD|NA|

-->