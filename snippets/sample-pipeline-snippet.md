

The following section contains a sample pipeline that you can refer to estimate effort required for migration.


## Webapp E2E template



### Who should use the Webapp E2E template?

Devops engineers who need to deliver a compliant CI/CD pipeline for a standard web application (regardless of language) considering best practices and security aspects.

### Why should you use the Webapp E2E template?

Every E2E template includes:
- A compliant pipeline that ensures auto inclusion of checks, scan jobs, and reporting for you. You can apply the template to the compliant pipeline under **Project** > **Settings** > **Compliance framework**. 
- The skeleton abstracts that enables the devops engineers to focus only on how to build, test, and deploy the application while taking care of other considerations during usage.

## CI/CD Flow Diagram

To get started with the Webapp E2E template, refer to the flow diagram and [steps](#steps) in the next section.


```mermaid
flowchart TD
    subgraph "TEST.gitlab-ci.yml"
    s1[lint-job] --- s2[depcheck-job] 
    s2 --- s3[unit-test-job]
    end

    subgraph "BUILD.gitlab-ci.yml"
    b1[build-job] -.- a3["Update TEST.gitlab-ci.yml"] --> s1
    end

    subgraph "DEPLOY.gitlab-ci.yml"
    d1[deploy-testing-job]
    d3[deploy-final-job]
    end

    subgraph ".gitlab-ci.yml"
    d1 --> d2[wait-for-webapp-ready-job]
    r1[e2e-test-job] --> r2[e2e-report-job] 
    p1[publish-app-job] --> p2[pull-deploy-artefact]
    end

    subgraph "Webapp-Compliance"
      subgraph "Static-test"
      s3 -.-> j4[ship-fortify-sast-fod-with-report*]
      j4 --- j5[ship-nexus-iq-scan*]
      j5 --- j6[ship-sonarqube-scan*]
      end
      subgraph "Sign"
      j9[sign-artefact-job]
      end
      subgraph ".pre"
      j1[secret_detection] --- j2["dependency_scanning* (if any)"]
      j2 --- j3["sast* (if any)"]
      j3 -.- a2["Update BUILD.gitlab-ci.yml"] -.-> b1

      end
      subgraph "Runtime-test"
      d2 -.-> j7[dast*]
      j7 --- j8[ship-fortify-dast*]
      j8 -.-> r1
      end

      subgraph "Deploy-to-prod"
      p2 -.-> j10[verify-job] 
      j10 --- j11[verify-artefact-signature]
      j11 --- j12[scan-verified-job*]
      j12 -.-> d3
      end
    end

    subgraph "DEPLOY.gitlab-ci.yml"
    j6 -.- a4["Update DEPLOY.gitlab-ci.yml"] -.-> d1
    end

    subgraph ".gitlab-ci.yml"
    r2 -.-> j9
    j9 -.-> p1
    end

    n1([start]) --- a1["Update variables in .gitlab-ci.yml and project's CICD settings"] --> j1
    d3 --> n2([end])

    classDef default fill:#ffd,stroke:#cc7;
    classDef A fill:#ddd,stroke:#eee;
    class a1,a2,a3,a4 A;
    classDef F fill:#fff,stroke:#226;
    class .gitlab-ci.yml,BUILD.gitlab-ci.yml,TEST.gitlab-ci.yml,DEPLOY.gitlab-ci.yml F;
    classDef C fill:#fff,stroke:#226,stroke-dasharray: 5 5;
    class Webapp-Compliance,.pre,Static-test,Runtime-test,Sign,Deploy-to-prod C;
    classDef N fill:#eef,stroke:#226;
    class n1,n2 N;
```
```mermaid
flowchart LR
  subgraph "Legend"
  direction LR
  n1(start) --- a1["user's task"] ---> j1
  j1 -...-> j2
  j3 --> n2(end)
    subgraph "Compliance-Framework"
      subgraph "Stage"
      j2[optional-job*] --> j3[job]
      end 
    end
    subgraph "File"
    direction LR
    j1[job] 
    end
  end

    classDef J fill:#ffd,stroke:#cc7;
    class j1,j2,j3 J;
    classDef A fill:#ddd,stroke:#eee;
    class a1 A;
    classDef F fill:#fff,stroke:#226;
    class File,Legend F;
    classDef C fill:#fff,stroke:#226,stroke-dasharray: 5 5;
    class Compliance-Framework,Stage C;
    classDef N fill:#eef,stroke:#226;
    class n1,n2 N;
```

<!--![CI/CD Flow Diagram](./images/ci-cd-flow-diagram.png)-->

## Steps

To get started with the Webapp E2E template, complete the following steps:

1. **Add your webapp code** in the repository to build and deploy your webapp.
1. **Fill in `BUILD.gitlab-ci.yml`**

  Provide the relevant build job(s) to build your webapp, producing an artefact.  
  Expected format: `$OUTPUT_ARTEFACT`
1. **Fill in `TEST.gitlab-ci.yml`** 
  
  Provide the relevant test job(s) to test your webapp code. <!--Some examples provided are like unit testing, linting, dependency checks.--> This step is required because some testing (e.g., unit testing) is highly dependent on language or tools. 
  
  You can use the reporting feature of GitLab within the job. For more information, refer to the [GitLab reports](https://docs.gitlab.com/ee/ci/yaml/artifacts_reports.html) documentation. 
1. **Fill in `DEPLOY.gitlab-ci.yml`** 
  
  Provide the relevant deploy job(s) to deploy your webapp code. In the example, `deploy-testing-job` points to a testing environment while `deploy-final-job` points to a production environment.
  
  You can use `deploy-final-job` to test the deployment to final environment. The job is also referenced by the relative compliance pipeline. Therefore, you must not change the name of this job. This ensures that certain safeguarding measures are present before deploying to any high stake environment.
1. **Fill in variables in `.gitlab-ci.yml`**
  
  Provide values for variables for the pipeline to pass. The relative compliance pipeline that runs alongside with the main pipeline requires most of them. 
  
  If the compliance job fails, your overall pipeline will continue to pass. However, this may impact the quality or security aspects of your webapp.
1. **Provide sensitive variables**
    
  The sensitive variables provided below are required for the compliance to pass for your pipeline. You may consider adding them in your project's CI/CD variables.

    - Required: For Cosign artefacts:
      - COSIGN_PASSWORD
    - Optional: You must provide the following credentials if you want to use the specified tool:
      - For Sonarqube scan:
        - SONAR_TOKEN
        - SONAR_PROJECTKEY

  If credentials are not provided for the following tools, its corresponding GitLab Native Tools will be included in the pipeline.

  |Tools          |GitLab Native Tools| 
  |----------------|-----------|
  |Fortify SAST: <ul><li> FOD_PAT|[GitLab SAST](https://docs.gitlab.com/ee/user/application_security/sast/)|
  |Fortify DAST: <ul><li> FOD_PAT|[GitLab DAST](https://docs.gitlab.com/ee/user/application_security/dast/)|
  |Nexus IQ scan: <ul><li> NEXUS_IQ_USERNAME <li> NEXUS_IQ_PASSWORD <li> NEXUS_IQ_APP_ID <li> NEXUS_IQ_SCAN_OPTIONS (Optional; may be used to set scan for a stage for continuous monitoring by using the [--stage flag](https://help.sonatype.com/integrations/nexus-iq-cli)) <br> See [how to turn on Continuous Monitoring for an application](https://help.sonatype.com/iqserver/managing/policy-management/continuous-monitoring-of-applications).|[GitLab Dependency Scanning](https://docs.gitlab.com/ee/user/application_security/dependency_scanning/)|

    - The following are required for the Webapp E2E template: 
      >**Note:** These are not required for compliance.

      For Nexus Repository publish:
        - NEXUS_REPO_USERNAME
        - NEXUS_REPO_PASSWORD

1. **Apply compliance framework**
  
  From your project, select **Settings** > **General** > **Compliance framework** > **ship-hats-webapp-compliance**.
  
  For more information, refer to the [ship-hats-webapp-compliance](https://sgts.gitlab-dedicated.com/WOG/ship-hats-compliance#template-webapp-compliance) documentation. These are accessible after onboarding to SHIP-HATS 2.0.

## Considerations

When using this end-to-end template:
  - Do **not** change the stages as it might impact the working of its relative compliance pipeline.
  - You may add or remove the jobs in `BUILD/TEST/DEPLOY.gitlab-ci.yml` with `# do not change the name of this job without making updates to .gitlab-ci.yml` to suit requirements for your webapp. However, you must update the change to `.gitlab-ci.yml` accordingly as it makes references to these jobs.
  - The development of this template might not fit all use cases. If you have a use case that this template is unable to accommodate, you can either raise an issue with us to consider or you may consider raising a merge request to share your use case template as this is an open source project.

<!--
## Working examples 

- [Nodets webapp](https://sgts.gitlab-dedicated.com/WOG/GVT/ship/e2e-templates/examples/nodets-webapp)
- [Python webapp](https://sgts.gitlab-dedicated.com/WOG/GVT/ship/e2e-templates/examples/python-webapp)
- CTMO working example link.

-->
