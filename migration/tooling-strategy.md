
|Stage|Component|GitLab Native Tool|Alt Tools Available|Alt Tools Contract Details|Assessment|Recommendation|  
|---|---|---|---|---|---|---|
|Planning|IT Service Management|GitLab Service Desk|Jira Service Management (Cloud Enterprise)||Jira’s features are more advanced than GitLab Service Desk|Either, depending on agency’s preference|
|Planning|Issue Tracking|GitLab Issues|Jira (Cloud Enterprise) with unlimited number of sites<br>[Jira integrations with GitLab](https://docs.gitlab.com/ee/integration/jira/)||Jira’s features are more advanced than GitLab Issues|Either, depending on agency’s preference|
|Planning|Wiki|GitLab Wiki|Confluence (Cloud Premium)||Confluence’s features are more advanced that GitLab Wiki|Either, depending on agency’s preference|
|Building and Packaging|Source Code Management|GitLab SCM|-|-|NA|GitLab|
||Artefact Repo|GitLab Package Registry/GitLab Binary Repo|Nexus Repo by Sonatype Nexus||GitLab Native is good for most runtimes, while Nexus Repo supports more runtimes.|Nexus Repo + Nexus IQ<br>*use trusted external scanner|
|Testing|SAST (Static Application Security Testing)|GitLab SAST|Fortify SCA à migrating to Fortify On-Demand||GitLab supports 18 languages only, while SonarQube supports more than 20 languages|FOD, has verified sources |
|Testing|SAST (Static Application Security Testing)|GitLab Code Quality Scanning Tool<br>SonarQube vs. GitLab or GitLab|SonarQube Developer Edition (OnPrem) for code quality scanning||GitLab supports 18 languages only, while SonarQube supports more than 20 languages|Either.<br>GitLab<br>SonarQube - more langs, more features and more dev-centric (code recc. for code quality improvements)|
|Testing|Dynamic Application Security Testing (DAST)|GitLab DAST|Fortify Webinspect Enterprise à migrating to Fortify On-Demand||Dev experience not great for Fortify Webinspect, need a windows VM|FOD, backed by pen tester<br>GitLab browser-based analyser in beta, API-<br>SAST/DAST comparison report between GL and FOD on the same vulnerability app.|
|Testing|Software Composition Analysis (SCA)|GitLab Depency Scanning (new)|Nexus Lifecycle<br>Nexus IQ/Intelligence||Recommended to use GitLab Dependency Scanning that is available on Ultimate|Either <br>GitLab, for basic<br>Nexus - automation & coverage|
|Testing|Automated Testing||Selenium, Robot Framework, pCloudy|||no GL alt|
|Testing|Container Image Scanning|GitLab Container Scanning|Prisma Cloud||Prisma Cloud is a decent choice if the customer only needs basic vulnerability scanning; however, to properly secure their applications, they should consider a solution that includes good SAST and DAST scanners. Rather than using separate scanners to meet their needs, it will be much simpler and easier to use GitLab, which both has a wide range of scanning capabilities as well as a native integration with SCM. Additionally, GitLab is a Niche player in the Gartner Magic Quadrant for AST.|GitLab|



