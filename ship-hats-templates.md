# SHIP-HATS Templates

SHIP-HATS Templates aims to help users construct their CICD pipelines efficiently by providing blackbox building blocks for users to include in their pipelines. It favours "write once, used by many" and thus, it is open for Innersourcing. See [CONTRIBUTING.md](CONTRIBUTING.md) for more information on this.

The templates are constructed with the following as our main focus : 
- Security
- Modularity and Reusability
- Use of inhouse / OTS Gitlab security tools
- Use of libraries and docker images via Nexus Repo to prioritize trusted package managers and repositories
- Use of Gitlab native reporting tools wherever possible

## Available templates (First cut) : 

The team has completed some of the templates listed below as the first cut of the library. Hopefully, more contributions would come when like-minded colleagues who likes to "write once, used by many" coming onboard with their pipelines.

### SHIP-HATS testing / scanning templates :
* [Nexus IQ scan](templates#file-gitlab-ci-nexus-iq-scanyml)
* [Robot framework](templates#file-gitlab-ci-run-testyml)
* [FOD SAST](templates#file-gitlab-ci-run-fod-sastyml)
* [FOD DAST](templates#file-gitlab-ci-run-fod-dastyml)
* [Sonarqube Scan](templates#file-gitlab-ci-sonarqubeyml)
* [Sonarqube Scan for Maven](templates#file-gitlab-ci-sonarqubeyml)
* [Sonarqube Scan for .NET Core](templates#file-gitlab-ci-sonarqubeyml)
* [Aquasec Trivy scan](templates#file-gitlab-ci-aquasec-trivy-scanyml)
* [Prisma container scan](templates#file-gitlab-ci-run-hatstwistcliyml)
* [Kubesec scan](templates#file-gitlab-ci-k8yml)
* Purple hats
* [Pcloudy Tests](templates#file-gitlab-ci-pcloudy-testyml)
* [Generate FOD SAST and DAST reports](templates#file-gitlab-ci-create-fod-reportyml)

### Nexus Repo templates :
* [`docker pull` fr Nexus Repo](templates#file-gitlab-ci-nexus-docker-pullyml)
* [`docker push` to Private Repo](templates#file-gitlab-ci-docker-pushyml)
* [Configure to use Nexus Repo for NPM](templates#file-gitlab-ci-nexus-configureyml)
* [Maven artefact publish to Nexus Repo](templates#file-gitlab-ci-publish-to-nexusyml)
* [Nodejs artefact publish to Nexus Repo](templates#file-gitlab-ci-publish-to-nexusyml)
* [NuGet artefact publish to Nexus Repo using NuGet CLI](templates#file-gitlab-ci-publish-to-nexusyml)
* [NuGet artefact publish to Nexus Repo using dotNet CLI](templates#file-gitlab-ci-publish-to-nexusyml)

### Windows-related templates (WIP):
* .NET build and deploy using .net runners

### Common templates :
* [Readiness check for web application](templates#file-gitlab-ci-check-app-readinessyml)
* [Readiness check for docker service](templates#file-gitlab-ci-check-app-readinessyml)
* [AZ CLI invocation](templates#file-gitlab-ci-azureyml)
* [Depcheck for NPM projects](templates#file-gitlab-ci-nodejs-commonyml)
* [AWS identity federation](templates#file-gitlab-ci-awsyml)
* [AWS Secret Retrieval](templates#file-gitlab-ci-awsyml)
* [AWS EKS kubectl](templates#file-gitlab-ci-kubectl-awsyml)
* [Container Signing](templates#file-gitlab-ci-container-signingyml)
* [Blob Signing and Verification](templates#file-gitlab-ci-blob-signingyml)
* [Checksum Verification](templates#file-gitlab-ci-checksum-verifyyml)
* [Delete Images from GitLab Container Registry](templates#file-gitlab-ci-docker-deleteyml)
* SSH
* SCP
* WinRM

### End to End CI References (WIP):
* [.NET applications hosted in Azure App Service](https://gts.gitlab-dedicated.systems/ctmo/clglabnetapp)
* .NET docker application hosted in AWS Fargate
* Java application hosted in AWS EC2
* Java docker application hosted in AWS EKS
* [Node.js Typescript application hosted in Azure App Service](https://gts.gitlab-dedicated.systems/ctmo/clglabnodetsapp)

## How to use : 

### Templates:
Find the template that you need from list of templates above. They link directly to the usage guides of the templates. In most cases, unless for more advanced ones, you just need to: 
1. Use "extends" keyword 
2. Pass in the right variable in job script 
3. Pass in CICD variables for sensitive variables.

### Examples :
Each template have examples demonstrating its usage and you may find direct links from the respective template usage guides.

### Release Management: 
Upcoming. Discussion and POC @ https://gts.gitlab-dedicated.systems/templates/ship-hats-templates/-/issues/72
