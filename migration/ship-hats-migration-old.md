# Migration Approach

Following <!--table and--> image provide high-level migration phases and key activities. We will be iteratively adding more details. 

<!--
| **Phase** | **Sandbox Testing** | **Migration** |
| --- | --- | --- |
| Details | Prepare target environment<br>Configure pipeline in Sandbox| Migrate Source Code Repository<br>Configure pipeline in actual environment|
| Duration Choice | Choose from 4, 6, or 12 weeks option| Choose from 2, 4, or 6 weeks option |  
-->



![Migration Phases](./images/migration-phases.png ':size=80%')

<!--**Topics**
- [Prerequisites](#prerequisites)
- [Sandbox Testing](#sandbox-testing)
- [Migration](#migration)
- [Training](#training)
-->
<!--
## Prerequisites


### Bitbucket repository name guidelines

Make sure that your current Bitbucket Repository names adhere to the following guidelines:

- Cannot have spaces
- Cannot start with `-`
- Cannot end with `.git` or `.atom`
- Cannot start or end with special characters
- Cannot contain consecutive special characters


## Sandbox Testing


### Goal
Configure pipeline on the sandbox environments and test connectivity with your hosting environment. 

### Sandbox Migration Options
Agencies can opt for 4, 6, or 12 week Sandbox Migration depending on your DevSecOps maturity, team availability, and system readiness. We will open a booking system for you to submit your request. 

### Configure using Templates

We will provide a library of SHIP-HATS [Pipeline templates](pipeline-templates) that will simplify the effort to configure the pipeline. These templates will include the best practices in security compliance and the performance metrics. 

### Flow
We will test this flow during our 2.0 migration pilots and iteratively improve on it. Based on these tests, we can offer recommendations on effort estimation for your systems.  

1.	Clone your Project Repository from Bitbucket to SHIP-HATS 2.0. 
1.	Verify that the clone is successful.
1.	Define success criteria for the CI/CD pipelines.
1.	Use the templates from GovTech to configure CI Pipeline.
1.	Test run CI Pipeline.
1.	Established connectivity with your target environment 
1.	Use the templates from GovTech to configure CD Pipeline.
1.	Test run CD Pipeline with at least a deployment to UAT/pre-production environments.  

?> The pipeline(s) configured in Sandbox Migration will be reused and adapted for 2.0 Migration. 

For more information, refer to [Annex: Sandbox Testing Flow Details](ship-hats-migration-annex#sandbox-testing-flow-details).

-->
## Migration 

### Goal
After you have successfully tested in the **Setup & Test** phase, you can start migrating projects to SHIP-HATS 2.0. The migration is completed when you run your end-to-end CI/CD with tools in SHIP-HATS 2.0 with no dependencies on SHIP-HATS 1.0. 

### 2.0 Migration Options
Agencies can opt for 2, 4, or 6 weeks 2.0 Migration depending on project status and other dependencies. We recommended starting 2.0 Migration as soon as you sign off **Setup & Test** phase to maximize on the lessons learnt while avoiding any drift in source code and pipelines.
### Flow

We will test this flow during our 2.0 migration pilots and iteratively improve on it.  After GovTech  migrates the source code repository, the agency team can:
1.	Verify the source code migrated.
1.	Adapt and test CI/CD pipeline from the **Setup & Test** phase. 

For more information, refer to [Annex: Migration Flow Details](ship-hats-migration-annex#migration-flow-details).

## Training

Refer to the [Training](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/training) section in the [Getting Started](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/) documentation.
<!--

We will roll out multi-format training to ensure the teams are skilled for the migration and adoption of best practices. 

### Content
We are developing documentation and training material to:  
- Learn the tools with SHIP-HATS 2.0 
- Understand and use the pipeline templates for security and compliance best practices

The content will be tailored for Project Managers, Business Analysts, and will provide a deeper technical training for Developers. The training will be open for both public officers and vendors. 

Training format will include self-paced materials, monthly webinars, and hands-on workshop. We will announce training schedule in Q2' FY22. 
-->

<!--
OLD CONTENT


## Prerequisites


### Bitbucket repository name guidelines

Make sure that your current Bitbucket Repository names adhere to the following guidelines:

- Cannot have spaces
- Cannot start with `-`
- Cannot end with `.git` or `.atom`
- Cannot start or end with special characters
- Cannot contain consecutive special characters


## Sandbox Testing


### Goal
Configure pipeline on the sandbox environments and test connectivity with your hosting environment. 

### Sandbox Migration Options
Agencies can opt for 4, 6, or 12 week Sandbox Migration depending on your DevSecOps maturity, team availability, and system readiness. We will open a booking system for you to submit your request. 

### Configure using Templates

We will provide a library of SHIP-HATS [Pipeline templates](pipeline-templates) that will simplify the effort to configure the pipeline. These templates will include the best practices in security compliance and the performance metrics. 

### Flow
We will test this flow during our 2.0 migration pilots and iteratively improve on it. Based on these tests, we can offer recommendations on effort estimation for your systems.  

1.	Clone your Project Repository from Bitbucket to SHIP-HATS 2.0. 
1.	Verify that the clone is successful.
1.	Define success criteria for the CI/CD pipelines.
1.	Use the templates from GovTech to configure CI Pipeline.
1.	Test run CI Pipeline.
1.	Established connectivity with your target environment 
1.	Use the templates from GovTech to configure CD Pipeline.
1.	Test run CD Pipeline with at least a deployment to UAT/pre-production environments.  

?> The pipeline(s) configured in Sandbox Migration will be reused and adapted for 2.0 Migration. 

For more information, refer to [Annex: Sandbox Testing Flow Details](ship-hats-migration-annex#sandbox-testing-flow-details).


## Migration 

### Goal
After you have successfully tested in the sandbox environment, you can start migrating projects to SHIP-HATS 2.0. The migration is completed when you run your end-to-end CI/CD with tools in SHIP-HATS 2.0 with no dependencies on SHIP-HATS 1.0. 

### 2.0 Migration Options
Agencies can opt for 2, 4, or 6 weeks 2.0 Migration depending on project status and other dependencies. We recommended starting 2.0 Migration as soon as you sign off sandbox testing to maximize on the lessons learnt while avoiding any drift in source code and pipelines.
### Flow

We will test this flow during our 2.0 migration pilots and iteratively improve on it.  After GovTech  migrates the source code repository, the agency team can:
1.	Verify the source code migrated.
1.	Adapt and test CI/CD pipeline from the Sandbox Testing. 

For more information, refer to [Annex: Migration Flow Details](ship-hats-migration-annex#migration-flow-details).

## Training

Refer to the [Training](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/training) section in the [Getting Started](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/) documentation.


-->