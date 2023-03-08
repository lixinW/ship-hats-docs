Following section provides tooling assessment and strategy to make the most of SHIP-HATS 2.0 offering.

- All tools (both GitLab Native and Alternatives) enable compliance with [IM8 DevSecOps](https://intranet.mof.gov.sg/portal/IM/Themes/IT-Management/Security/Topics/Application-Development-Security.aspx) policy under Application Development Security. 
- Using GitLab Native only will result in a lower subscription cost. Alternative tools will be available as add-ons in the pricing table.
- The SHIP-HATS team has prepared pipeline templates for both GitLab Native and alternative tooling options.
- Dashboards within GitLab are most useful when most GitLab Native components are in use.


## Assessment

|Stage|GitLab Native|Alternative Tool|Assessment|
|---|---|---|---|
|Access|TechPass & SEED|TechPass & SEED|NA
|Plan|GitLab Issues|Jira |[GitLab Wiki vs Atlassian Jira](#gitlab-issues-vs-atlassian-jira)|	
|Plan|GitLab Wiki| Confluence |[GitLab Wiki vs Atlassian Confluence](#gitlab-wiki-vs-atlassian-confluence)|	
|Plan|Gitlab Security Dashboard|NA|NA	
|Build|GitLab CI/CD|NA|NA|
|Build|GitLab Package Registry|Nexus Repository Pro|[GitLab vs Nexus](#gitlab-vs-nexus)|
|Build|GitLab Dependency Scanning|Nexus Intelligence/Nexus IQ Server|[GitLab vs Nexus](#gitlab-vs-nexus)|
|Build Testing|GitLab SAST + [XCA SAST by GovTech](#extended-code-analysis)|Fortify-on-Demand SAST + [XCA SAST by GovTech](#extended-code-analysis)|[GitLab vs Fortify-on-Demand](#gitlab-vs-fortify-on-demand)|
|Other Tests|GitLab Code Quality Scanning Tool <br> <br>**Note:** Please refer to [our recommendation and assessment](#gitlab-vs-sonarqube) below before choosing GitLab Code Quality Scanning Tool.|SonarQube Community/Developer Edition|[GitLab vs SonarQube](#gitlab-vs-sonarqube)|
|Other Tests|GitLab DAST|Fortify-on-demand DAST|[GitLab vs Fortify-on-Demand](#gitlab-vs-fortify-on-demand)|
|Other Tests|GitLab Container Scanning|NA|NA|
|Other Tests|NA|pCloudy Test Farm|NA|
|Other Tests|GitLab (Pa11y)|Purple HATS|GitLab (Pa11y) vs Purple HATS(Coming soon!)|
|Deploy & Release|GitLab CI/CD|NA|NA|


## GitLab Issues vs Atlassian Jira

Refer to [Jira vs GitLab](https://about.gitlab.com/devops-tools/jira-vs-gitlab/) for a comparison.

## GitLab Wiki vs Atlassian Confluence 

Coming soon!


## GitLab vs Nexus 

|Feature|GitLab|Nexus Repo & Nexus Intelligence|
|---|---|---|
|Packages Supported|Refer to the [GitLab Supported package managers](https://docs.gitlab.com/ee/user/packages/package_registry/?_gl=1*1l2qds1*_ga*MTQzMDQ0ODE5NS4xNjUzOTYxMTM2*_ga_ENFH3X7M5Y*MTY2NTUwMTY2OS4yNC4xLjE2NjU1MDIxNDUuMC4wLjA.#supported-package-managers) documentation for details. |Supports more package types. Refer to the [Nexus Repo](https://www.sonatype.com/products/nexus-repository?topnav=true) documentation for details. |
|Scanning Capabilities|Dependency Scanning is frequently bundled together with Container Scanning and License Compliance to provide an overall Software Composition Analysis (SCA) solution within the Application Security Testing (AST) market. GitLab was recently named as a [Challenger in the 2021 Magic Quadrant for Application Security Testing](https://about.gitlab.com/analysts/gartner-ast21/).<br><br>Refer to the [GitLab Category Direction - Dependency Scanning](https://about.gitlab.com/direction/secure/composition-analysis/dependency-scanning/) documentation for more details.|SCA scanning can be automated to scan and remediate the artifacts in the repository once to produce components that the entire organization can use.|
|Repo Sharing|Repos are tied to projects.|Central repo sharing across projects. <br><br> Nexus IQ performs scheduled background scanning (SCA) of binaries and repos.|

For more information, refer to the GitLab [Sonatype Nexus Repository vs. GitLab](https://about.staging.gitlab.com/devops-tools/sonatype-nexus-repo-vs-gitlab.html) documentation.


## GitLab vs SonarQube

<!--!> We recommend that agencies who require code quality scanning to choose the alternative offering, SonarQube - at the moment, SHIP-HATS does not offer shared runners that can support GitLab's Code Quality Scanning tool which requires the runner to be either in privileged mode to support DinD or a runner with Docker socket binding. However, if you wish to still use GitLab's Code Quality Scanning tool, please note that you will have to set up your own self-hosted runners after performing risk assessment, and obtaining approval from your IT Steering Committee.-->

|Feature|GitLab|SonarQube|
|---|---|---|
|Recommendation||We recommend that **agencies who require code quality scanning to choose SonarQube** (the alternative offering). Currently, SHIP-HATS does not offer shared runners that can support GitLab's Code Quality Scanning tool which requires the runner to be either in privileged mode to support DinD or a runner with Docker socket binding. However, if you want to still use GitLab's Code Quality Scanning tool, please note that you will have to set up your own self-hosted runners after performing risk assessment, and obtaining approval from your IT Steering Committee.|
|Languages Supported|Refer to the [SonarQube vs. GitLab](https://about.staging.gitlab.com/devops-tools/sonarqube-vs-gitlab.html) documentation for details. |Community Edition* supports static code analysis for 17 languages: `Java`, `C#`, `JavaScript`, `TypeScript`, `CloudFormation`, `Terraform`, `Kotlin`, `Ruby`, `Go`, `Scala`, `Flex`, `Python`, `PHP`, `HTML`, `CSS`, `XML`, and `VB.NET` <br><br>Developer Edition supports static code analysis for 7 more languages: `C`, `C++`, `Obj-C`, `Swift`, `ABAP`, `T-SQL`, `PL/SQL`<br><br>*SHIP-HATS provides a self-hosted (in-country) version of SonarQube Community and Developer Editions|
|Gating|-|SonarQube supports gating that can be configured via its UI. Without this gating capability, the alternative will be to script the gates into the pipeline. This would require additional effort and should be templated.|
|Security Reports	|GitLab Ultimate automatically includes broad security scanning with every code commit including Static and Dynamic Application Security Testing, along with dependency scanning, container scanning, and license management.|	SonaQube provides a more detailed report than GitLab's SCA report. It contains information on code smell, portfolio, reliability, maintainability, etc. that are more developer-centric than security-centric.<br><br> SonarQube can report on unit tests, code coverage, and complexity. 




## GitLab vs Fortify-on-Demand 

If you are **new to application security testing**, we recommend GitLab SAST/DAST as it will be simpler to integrate with GitLab SAST/DAST than Fortify-on-Demand’s extensive product offering that could be overwhelming for a new user.

|Feature|GitLab|Fortify-on-Demand|
|---|---|---|
|Languages Supported|`.Net`, `Java`, `Javascript`, `Python`, `Typescript`, `C`, `C++`, `React`, `RubyonRails`, `Go`, `Kotlin`, `Elixir`, `Kubernetes`|`ABAP/BSP`, `ActionScript`, `Apex`, `ASP.NET`, `C# (.NET)`, `C/C++`, `Classic`, `ASP` (with VBScript), `COBOL`, `ColdFusion CFML`, `Go`, `HTML`, `Java` (including Android), `JavaScript/ AJAX`, `JSP`, `Kotlin`, `MXML (Flex)`, `Objective C/C++`, `PHP`, `PL/SQL`, `Python`, `Ruby`, `Swift`, `T-SQL`, `VB.NET`, `VBScript`, `Visual Basic`, `XML`, `JSON/YAML` and `Docker` (Dockerfile)<br><br> If  you are using a language that is not supported by GitLab Package DAST/SAST , please use Fortify-Demand.|
|Data Sources |GitLab’s data is mostly open-sourced. <br><br><br><br>Compatible with industry standards.| Fortify-on-Demand has verified data sources. <br>Please use Fortify-on-Demand if you require verified data sources. <br><br>Compatible with industry standards. |
|Remediation|Basic services | Fortify provides remediation advice, which is more detailed than GitLab native. |

### SAST

- Semgrep is the highly potential tool and supports Java, javascript, TypeScript, React, Python and Go.
- For `GO` and `Elixir`, GitLab is recommended whereas FOD supports many other language stack. 
- For full stack framework such as `node.js`, `react`, and `ruby`, GitLab tool stack is helpful in scanning respective languages. 
- For other veteran languages, both FOD and Gitlab are recommended. 
- FOD offers better security. 

The following table lists supporting languages and its respective SAST tool set under GitLab offering: 

|Language|GitLab SAST Tool|
|---|---|
|.Net core, .Net Framework	|Security Code Scan
Java	|Semgrep, SpotBugs
Javascript|	Semgrep, ESlint Security Plugin
TypeScript	|Semgrep, ESlint Security Plugin
Node.js	|NodeJsScan 
React	|Semgrep, ESlint React Plugin
Python	|Semgrep, Bandit (pip)
Ruby on Rails|	Brakeman
Go	|GoSec, Semgrep
Kubernetes Manifests|	Kubesec
Kotlin	|MobSF, SpotBugs with FindSec plugin
Elixir	|SoBelow


### DAST

- In [GitLab recommended ZAP](https://docs.gitlab.com/ee/user/application_security/dast/), the number of vulnerabilities and number of false positives are less. 
- In WebInspect, the scan coverage is vast and number of vulnerabilities are far higher when compare to Gitlab DAST.
- ZAP have less number of security checks whereas FOD have complex security engine, which will conduct lot of security checks. Therefore, the scan is extensive in FOD compared to ZAP. 


<!--## GitLab (Pa11y) vs Purple HATS

Coming soon!-->