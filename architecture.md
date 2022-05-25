# SHIP-HATS Architecture

**Commercially Off the Shelf (COTS)** tools are available on SHIP-HATS with the right security and compliance settings. The following diagram shows how they work together to provide a seamless platform. For more information on tools, refer to the [Tools in SHIP-HATS](#tools-in-ship-hats) section.

![ship archi](ship-archi.png)

## Terminology
The above diagram uses the following terminology:

| **Term** | **Description** |
| --- | --- |
| GSIB | Government Standard Image Build|
| GCC | Government Commercial Cloud |
| SOE | Standard ICT Operating Environment|
| VPC | Virtual Private Cloud|
| TWG | Transit Gateway|

## Tools in SHIP-HATS
 
The following section provide links to documentation and tutorials to learn the tools offered under **SHIP-HATS**. Note that these are not specific to SHIP-HATS but a pre-cursor to enable you to use these tools within SHIP-HATS effectively.  


| **Tool** | **Description** | **Links** |
| --- | --- | --- |
| **Jira** | Project management tool that is used to view, track, and manage projects and the progress of your team's tasks or bugs for a sprint displayed in an agile board. | [Overview](https://www.atlassian.com/software/jira/guides/getting-started/overview) & [Tutorials](https://www.atlassian.com/software/jira/guides/getting-started/basics#step-2-pick-a-template) | 
| **Confluence** | Shared space for collaboration to view, access, and manage all tasks and problems for the entire team enforces the idea of shared responsibility. Shared knowledge and environment also encourages experimentation. | [Overview](https://www.atlassian.com/software/confluence/guides/get-started/confluence-overview#hosting-options) & [Tutorials](https://www.atlassian.com/software/confluence/guides/get-started/set-up) | 
| **Bitbucket** | Version control tool for software engineering team to collaborate on source code and integrate with software development tools to automate the release pipeline. | [Overview](https://www.atlassian.com/software/bitbucket/guides/getting-started/overview) & [Tutorials](https://www.atlassian.com/software/bitbucket/guides/basics/bitbucket-interface#your-work) |

### Build Tool

| **Tool** | **Description** | **Link** |
| --- | --- | --- |  
| **Bamboo** | Tool for Continuous Integration that enables constant merging and testing of code, which leads to early defect detection and saves time to fix merge issues. This also enables the development teams to receive rapid feedback on their work. |  [Overview](https://www.atlassian.com/software/bamboo) |

### QA & Security Tools

| **Tool** | **Description** | **Links** |
| --- | --- | --- |
| **Nexus Repository Manager** | Tool for artifact management to ensure that the development, build, and production environments deploy consistent artifacts. This tool helps in reducing errors due to differences in build artifacts. This tool also provides version control for release artifacts for better control and easier rollback. | [Overview](https://www.sonatype.com/product-nexus-repository) |  
| **Nexus IQ** | Tool for scanning application binaries and open source libraries for all popular formats, including NPM, Nuget, Maven, Bowser, and more. This tool continuously monitors and alerts users of open-source vulnerabilities. | [Overview](https://www.sonatype.com/nexus-iq-server) |  
| **pCloudy Test Farm** | Tool to run automated tests on browsers (desktop and mobile) and mobile apps. Automation is triggered from Bamboo using the [Robot Framework](https://robotframework.org/). | [Overview](https://www.pcloudy.com/) |
| **SonarQube** | Automatic code review tool to detect bugs, vulnerabilities, and code smell. 15 supported base languages include C#, Java, CSS, VB.NET, JavaScript, XML, TypeScript, Python, Flex, Kotlin, PHP, Go, Ruby, HTML, and Scala. | [Overview](https://docs.sonarqube.org/latest/) |
| **Fortify WebInspect** | Dynamic Application Security Testing (DAST) tool that identifies vulnerabilities in web applications and APIs while they are running in production. | [Overview & Free Trial](https://www.microfocus.com/en-us/products/webinspect-dynamic-analysis-dast/overview) |  |
**Fortify SCA** | Static Application Security Testing (SAST) tool that identifies security vulnerabilities in software source code. Developers find and fix security defects in real-time during the coding process, with integrations to IDEs. | [Overview](https://www.microfocus.com/en-us/products/static-code-analysis-sast/overview) |  