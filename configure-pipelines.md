# Step 4: Configure Pipelines

?> Complete these steps in the **[GitLab](https://sgts.gitlab-dedicated.com/) tool**.


## Step 4a: Set up Remote runners [Optional]

> **Note:** You can complete this step in parallel with [Step 4b: Configure CI/CD Pipeline](#step-4b-configure-cicd-pipeline).

If you are using Remote [Runners](runners), you can connect to SHIP-HATS using:
- [AWS VPC Endpoint](aws-vpc-endpoint) <br>or 
- [IPsec Tunnel](ipsec-tunnel)


For more information, refer to [Set up Runners](gitlab-runners).

## Step 4b: Configure CI/CD Pipeline

1. Decide the CI approach, and then copy the [E2E Template](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=e2e-templates) into your own repository and update the project variables. Refer to [Pipeline architecture by GitLab](https://docs.gitlab.com/ee/ci/pipelines/pipeline_architectures.html) & [Continuous integration best practices by GitLab](https://about.gitlab.com/topics/ci-cd/continuous-integration-best-practices/). 
1. **[Optional]** Modify your pipeline using the Modular template. If the E2E template does not meet your requirement, you can modify your pipeline using the [Common Templates (Modular)](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=common-templates) or [Reference Pipeline](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates?id=reference-pipelines) for any additional capabilities. 
    
    >**Tip:** [View Sample Pipeline](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/sample-pipeline).
    
1. Apply [Compliance Framework](compliance-framework).	
1. Decide the CD approach, and then execute deployment successfully on non-production and production environments. Refer to [Gitlab CD Approaches](https://sgts.gitlab-dedicated.com/groups/wog/gvt/ctmo/reference-pipelines/-/wikis/Gitlab-CD-Approaches) (accessible via SHIP-HATS GitLab account).


?> After you have completed above setup, you can use **[GitLab dashboards](dashboards)** and review **[DORA metrics](dashboards)** to ensure BAU in GitLab.


## Performed by (roles)

|Performed by (roles)| Description|  
|---|---|
**All** |All Customers team members involved in the onboarding process
**Agency PM**| The Project Manager that acts on behalf of the Customer Agency (needs to be a public officer).
**Technical POC** |The Technical Point of Contact, typically someone with some management authority & the most technically competent member within the Customer Agency team (can be in-house or outsourced).

<!--
|Activity|Description|Performed by|GovTech Supporting Guide|  
|---|---|---|---|
|Set up Remote runners [Optional]<br><br>**Note:** You can complete this step in parallel with Configure CI Pipeline|If you are using Remote runners, you can connect to SHIP-HATS using:<br><br> **AWS VPC Endpoint** <br><br>or<br><br> **IPsec Tunnel**|Technical POC|[Runners](runners)<br><br>[Set up Runners](gitlab-runners)<br><br>[AWS VPC Endpoint](aws-vpc-endpoint)<br><br>or <br><br>[IPsec Tunnel](ipsec-tunnel)
|Configure CI pipeline|1. Copy the E2E template into your own repository and update the project variables|Technical POC|[E2E Templates](pipeline-templates)
||2. Modify your pipeline using the Modular template [Optional]<br><br>This is an optional step. If the E2E template does not meet your requirement, you can modify your pipeline using the Modular templates for any additional capabilities.|Technical POC|[Common Templates (Modular)](pipeline-templates)
||3. Apply Compliance Framework|Technical POC|[Compliance Framework](compliance-framework)
|Configure CD pipeline <br>(non-production & production)| Execute deployment successfully on non-production and production|Technical POC|[E2E Templates](pipeline-templates)
-->