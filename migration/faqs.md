# FAQs

This section provides answers to frequently asked questions.

## Timeline FAQs

>**Tip:** Click the triangle or question to view the answer.

<details>
  <summary><b> When can new subscribers onboard to SHIP-HATS 2.0? </b></summary><br>

New subscribers can onboard SHIP-HATS 2.0 from November 2022. For more information, refer to the [Timelines](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=timelines) documentation.  
If your project timelines require you to start earlier, please log a ticket at [go.gov.sg/she](http://go.gov.sg/she) with details of your project needs and teams. SHIP-HATS team will work with you to plan the way forward.

</details>
<br>

<details>
  <summary><b>  What is the migration window for existing SHIP-HATS users?</b></summary><br>

Existing subscribers can migrate to SHIP-HATS 2.0 from November 2022. The specific date of GA will be announced closer to the date. 

- Users with Fortify SCA & WebInspect must complete migration by 31 July 2023. If you are a Fortify user and if this migration timelines does not work, please log a ticket at [go.gov.sg/she](http://go.gov.sg/she) with details of your project needs.
- Users without Fortify SCA & WebInspect must complete migration within 1 year from the date of SHIP-HATS 2.0 GA.
</details>
<br>

<details>
  <summary><b> What are decommissioning dates of SHIP-HATS 1.0 products? </b></summary><br>

Please refer to the [Key tool decommission dates](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=key-tool-decommission-dates) documentation. 
</details>
<br>

<details>
  <summary><b> When is the planned migration of Self-hosted Jira and Confluence to Cloud? </b></summary><br>

We will provide more details by Q3 FY22.
</details>
<br>

<details>
  <summary><b>  Is there a roadmap to decommission Alternative Tools and replace with GitLab Native tools?
</b></summary><br>

We review and assess all the tools at regular frequency. If GitLab native tools meet our requirements, we may plan for decommissioning the Alternative Tools which will help us to provide more cost saving to the Agencies. However, this would be done in phases with clear communication on timelines.

Please refer to [timelines documentation](ship-hats-migration-what-to-expect) for planned decommission.

</details>
<br>

<details>
  <summary><b>  Is there any hard deadline for existing project that already implement SHIP-HAT 1.0 to move to 2.0?	
</b></summary><br>

Yes. Refer to the [What to Expect > Timelines](ship-hats-migration-what-to-expect) section in the documentation.

</details>
<br>


## Access FAQs

>**Tip:** Click the triangle or question to view the answer.

<details>
  <summary><b>How can I access SHIP-HATS 2.0?</b></summary><br>

SHIP-HATS 2.0 tools including Portal can be accessed using GSIB or SEED-enabled developer device authenticated using TechPass. For more information, refer to the [Architecture > User Access](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/architecture?id=user-accessibility) documentation in the [SHIP-HATS Getting Started](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/) documentation.

</details>
<br>

<details>
  <summary><b> When will OpenVPN be decommissioned? </b></summary><br>

OpenVPN will be decommissioned by 31 December 2022. From 1 January 2023, user must use TechPass to log in to SHIP HATS 1.0 or 2.0. For more information, refer to the [Key tool decommission dates](https://docs.developer.tech.gov.sg/docs/ship-hats-migration/ship-hats-migration-what-to-expect?id=key-tool-decommission-dates) documentation. 

</details>
<br>

<details>
  <summary><b> Our system is on SHIP-HATS 1.0. Will I need SEED & TechPass from 1 January 2023? </b></summary><br>

Yes. All SHIP-HATS users have been invited to onboard to TechPass. By 31 December 2022, users must switch from OpenVPN to TechPass. If you have not received the onboarding email, please send an email to [enquiries_ship@tech.gov.sg](enquiries_ship@tech.gov.sg)
</details>
<br>

<details>
  <summary><b> I have issues onboarding to SEED & TechPass. What can I do? </b></summary><br>

[Raise a service request with the TechPass team](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/support/overview).
</details>
<br>

<details>
  <summary><b> Can SHIP-HATS 2.0 tools like Gitlab and Fortify-on-demand be on a private network. For example via VPC endpoints? </b></summary><br>

Yes.
</details>
<br>


## Product FAQs


### Selection

>**Tip:** Click the triangle or question to view the answer.

<details>
  <summary><b> Why did we pick GitLab for SHIP-HATS 2.0? 
 </b></summary><br>

We selected GitLab based on following:

- Proof of concepts and extensive testing by our developers 
- Timely availability of a managed dedicated SaaS in Singapore
- Progressive product roadmap and more integrated CI/CD features in the platform
- TRA clearance with CSG and IDSC acceptance of residual risks 
</details>
<br>

<details>
  <summary><b>  What is the data classification of the systems that can be onboarded to SHIP-HATS 2.0?
</b></summary><br>

We are currently supporting systems that are classified as Restricted and below.  
If you have a need to support systems that are above this classification, please log a ticket at [go.gov.sg/she](http://go.gov.sg/she). The demand estimation can help us to present the case to the leadership.

</details>
<br>

### Tools

>**Tip:** Click the triangle or question to view the answer.

<details>
  <summary><b>  How are Alternatives Tools linked in the CI pipeline on GitLab?
</b></summary><br>

There is no concept of plugin for the CI/CD pipeline within GitLab. 

</details>
<br>

<details>
  <summary><b>  How do we know which programming languages are supported in GitLab?
</b></summary><br>

Refer to our [tooling strategy documentation](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ship-hats-tools?id=tooling-strategy) for specific information.

</details>
<br>

<details>
  <summary><b>  Will the pull request history be migrated from Bitbucket to GitLab repo?
</b></summary><br>

Yes, the pull request history will be able to be migrated from Bitbucket to GitLab repo.
</details>
<br>

<details>
  <summary><b>  How will JIRA issues and comments history be migrated to GitLab issues?
</b></summary><br>

For Jira issues, the comments will not be migrated. These will be resolved to strings instead of readings. If Jira is integrated with GitLab, the Jira links in the comments will be resolved.  

</details>
<br>

<details>
  <summary><b>  We are currently relying on Fortify in SHIP-HATS 1.0. If we select Fortify on Demand in SHIP-HATS 2.0, will the audit from SHIP-HATS 1.0 be migrated to 2.0 as well?
</b></summary><br>

Yes. All the audit findings and issue suppression will be migrated to Fortify on Demand. These will include all the attributes that have been set up in your application.

</details>
<br>

<details>
  <summary><b>  Will repo mirroring be enabled?
</b></summary><br>

[Repo mirroring](https://docs.gitlab.com/ee/user/project/repository/mirror/) is enabled by default. For specific use case, please write to us at [go.gov.sg/she](http://go.gov.sg/she).


</details>
<br>

<details>
  <summary><b>  Can we set up our own compliance template?	
</b></summary><br>

Yes, you can create your own compliance template. We do recommend that you build it on top of SHIP-HATS 2.0 templates provided. However, it must be contributed to the project before it can be applied to the project.  

For more information, refer to following documentation:
- [Pipeline templates](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-templates)
- [sample pipeline](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/sample-pipeline)
- [GitLab innersourcing](https://about.gitlab.com/solutions/innersource/)
</details>
<br>

<details>
  <summary><b>  Can I use a combination of GitLab Native and Alternative Tools?
</b></summary><br>

Yes. For detailed information, refer to the assessment in the [tooling strategy](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ship-hats-tools?id=tooling-strategy) documentation.
</details>
<br>

<details>
  <summary><b>  If you use Jira for issue tracking, will it still populate the Dora Metrics dashboard?	
</b></summary><br>

No. For more information, refer to [Dashboards](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/dashboards) section in the [Getting Started](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/) documentation. 

</details>
<br>

<details>
  <summary><b>  What do I do, if I don't find a SHIP-HATS template that I need?  
</b></summary><br>

If you don't find a E2E or modular template you are looking for, raise a request [http://go.gov.sg/she](http://go.gov.sg/she). Based on the demand we will create. If you've created a template and please contribute back in GitLab.
</details>
<br>

<details>
  <summary><b>  Is there any standardised Terraform scanning tool (e.g., tfsec) provided in SHIP-HATS 2.0?	
</b></summary><br>

Team will revert with more information.

</details>
<br>




### Architecture - Runners

>**Tip:** Click the triangle or question to view the answer.


<details>
  <summary><b> What are the types of runners available on SHIP-HATS 2.0?
 </b></summary><br>


There are 3 types of runners available for our subscribers:

- SHIP-HATS Shared Runners are self-hosted runners in a scalable environment.
- GitLab Shared Runners are SaaS based shared runners. 
- Agency-hosted Remote Runners are dedicated runners set up in the agency environment. 

</details>
<br>

<details>
  <summary><b> Will the subscribers be able to host their our own GitLab runners?
 </b></summary><br>

Yes, the subscribers can host remote runners in their own environment. 

</details>
<br>

<details>
  <summary><b> What are the agents that we use for deployment? </b></summary><br>

Runners (Shared or Dedicated) are used for deployment in SHIP-HATS.

</details>
<br>


<details>
  <summary><b> Can the shared runner access our servers in GCC or OnPrem? </b></summary><br>

For GCC, the users can use SHIP-HATS Shared Runner and for OnPrem, users need an Agency-hosted Remote Runner. 

</details>
<br>




<details>
  <summary><b>Can SHIP-HATS integrate with other SaaS such as Salesforce? </b></summary><br>

Every SaaS has different integration capability. Therefore, it depends on the product.

</details>
<br>



<details>
  <summary><b> Can the GitLab Shared Runner download packages from the internet?
 </b></summary><br>

All the packages from the internet have to proxy through Nexus on SHIP-HATS for security reasons. 

</details>
<br>



### Pipeline and Usecases



>**Tip:** Click the triangle or question to view the answer.


<details>
  <summary><b> Can Agencies use SHIP-HATS 2.0 to run Infrastructure-as-Code such as Terraform or Ansible to build the infra on GCC?
 </b></summary><br>

Yes.
</details>
<br>

<details>
  <summary><b>  How can I understand more about CD and deployment?</b></summary><br>

Watch out for [documentation](https://go.gov.sg/ship-hats-docs) and [training](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/training) in early Q3 FY22. 

</details>
<br>

<details>
  <summary><b> Can the CI/CD pipeline on SHIP-HATS 2.0 integrate with a webhook in the Internet? </b></summary><br>

If GitLab supports the webhook, it can be integrated.
</details>
<br>
 


### 1.0 to 2.0 Migration

>**Tip:** Click the triangle or question to view the answer.


<details>
  <summary><b> How are the permissions and rules set in Bitbucket migrated to GitLab? </b></summary><br>

Repo Permissions (such as branch permissions and merge strategy) have to be reset in GitLab.  User permission have to be mapped to the equivalent in user roles in GitLab.

</details>
<br>


<details>
  <summary><b> When will Gitlab and JIRA integration be available? </b></summary><br>

All users will have Jira in the SHIP-HATS 2.0 tools when we go GA in November 2022.

</details>
<br>


<details>
  <summary><b> Can I volunteer for migration pilot? </b></summary><br>

Currently, we have closed invitations for Pilots. If you have a business urgency, please log a ticket at [go.gov.sg/she](http://go.gov.sg/she).
</details>
<br>

<details>
  <summary><b>  What are the migration cost supports available for existing SHIP-HATS users?
</b></summary><br>

SHIP-HATS team is supporting through free trainings - webinars and hands-on workshops to enable the agencies on SHIP-HATS 2.0. We are also providing [pipeline templates](pipeline-templates) to reduce the pipeline set up effort. Since the migration effort complexity varies for each team, the actual migration costs should be planned by the agencies.


</details>
<br>

## Training FAQs

>**Tip:** Click the triangle or question to view the answer.

<details>
  <summary><b>  Any GitLab courses for BAs managing CI/CD to up-skill so we can manage DevOps better?	
</b></summary><br>

Refer to the following resources:
- [Learning Events](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/learning-events) for our upcoming webinars and trainings.
- [Self-paced trainings](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/self-paced-trainings) for self-paced trainings and GitLab content.

</details>
<br>

<details>
  <summary><b>  Any cost difference between guided and self-led support Migration?
</b></summary><br>

Both support options are free. We offer two options to provide flexibility for agencies to choose the option that suits their setup better and manage their migration. 
</details>
<br>