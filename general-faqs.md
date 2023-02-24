# FAQs

## Onboarding FAQs

?>**Tip:** Click the triangle to view the answer.

<details>
  <summary style="font-size:20px"><b> Will the default gitlab project’s parent group name that is created for our agency always be the Ship subscription name?	
 </b></summary><br>

Yes, the default Gitlab project’s parent group name that is created for agency will always be the same as SHIP-HATS subscription name. Therefore to rename the parent group, the SHIP-HATS subscription title will need to be renamed as well.

Should you decide to change the parent group name & subscription title, please [raise a service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11). In the ticket's Summary field, please indicate `SHIP-HATS 2.0 GitLab - <your request>`

For more information on the groups, please refer the link:

https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/architecture?id=gitlab-groups

</details>

---

<details>
  <summary style="font-size:20px"><b>What need to do if I encountering "Cannot connect to the Docker daemon at unix:///var/run/docker.sock." for docker build cmd. </b></summary><br>

Try to consider using ship-hats-templates to overcome these problems.

https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates

Common Functions: https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/blob/main/templates/.gitlab-ci-common.yml
</details>

---

<details>
  <summary style="font-size:20px"><b>How can team do a docker image push to AWS ECR with shared_runner? Is there a template for this requirement?	</b></summary><br>

Please refer this COE template:

https://sgts.gitlab-dedicated.com/pipeline-coe/awscli-docker-image

</details>

---

<details>
  <summary style="font-size:20px"><b>What’s the meaning of Alternative tools (in the table with GitLab Native tools)? Can we use our own tools?</b></summary><br>

Alternative tools are tools from SHIP-HATS 1.0, where VPC endpoints are configured to take care of the connectivity for the tools and Gitlab. For tools that are not in the alternative tools list, agencies will need to setup the connectivity for their tools with GitLab.

</details>

---

<details>
  <summary style="font-size:20px"><b>Since the subscription model includes GitLab Native tools, do we still need to subscribe to other tools such as sonarqube? Is there a checklist on the difference between the tools that we can refer to? </b></summary><br>

This depends on the agencies’ use case. GitLab native tools may not be the best in class industry standards, hence alternatives tools are provided. Checklist for tooling strategy: https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ship-hats-tools
</details>

---


## Pipeline FAQs

?>**Tip:** Click the triangle to view the answer.


<details>
  <summary style="font-size:20px"><b> Currently developers with Developer role unable to see Merge button. How do I enable this without setting the role to Maintainer?		</b></summary><br>

Go to your project ==> settings/repository to make the necessary changes.

</details>

---

<details>
  <summary style="font-size:20px"><b>Will the GitLab Pages feature is expected to be available in SHIP 2? </b></summary><br>

Yes pages are in the roadmap. It is currently not available yet. ETA is Q1 2023. 
</details>

---

<details>
  <summary style="font-size:20px"><b>Will shared runners can fit for running large size docker images?	 </b></summary><br>

The shared runners will not be able to accommodate large size docker image. Hence, recommend to use  own runners where will have more control over the storage size of the runner itself.

Please refer published the steps on setting up own runners https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/gitlab-runners
</details>

---

<details>
  <summary style="font-size:20px"><b>How to update gitlab project and subgroup settings configurations as code? Eg. Adding members, their roles, and other project and group level settings.	</b></summary><br>

https://registry.terraform.io/providers/gitlabhq/gitlab/latest/docs

https://docs.gitlab.com/ee/user/project/code_owners.html
</details>

---

<details>
  <summary style="font-size:20px"><b>How to support service accounts that are not tied to a human, no techpass and seed for the purpose of automating updating git tags, scheduled pipelines' owner, etc?	</b></summary><br>

Going forward solution is to use auto generated CI tokens for all the tools need. This feature will be released into SHIP-HATS portal by Oct'22 end week. Post that, able to retrieve these CI tokens and update into their pipelines.	
</details>

---

<details>
  <summary style="font-size:20px"><b> Can I use autodevops with ship-hats 2.0?</b></summary><br>

Yes, autodevops is available. But we do encourage you to explore our E2E templates by SHIP as well. You can refer to our templates here: https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates

</details>

---

<details>
  <summary style="font-size:20px"><b>Can we have Mac OS runners in gitlab? </b></summary><br>

We do not have Mac OS runner support at the moment. For now we suggest that you could try hosting your own Mac OS runners.
</details>

---

<details>
  <summary style="font-size:20px"><b>Any tool provided for convert bamboo to gitlab yaml? </b></summary><br>

No we do not have any tools to convert bamboo to gitlab yaml. But the team working on streamlining bamboo pipelines to gitlab yaml. This is through the applying of our E2E templates here: https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates

</details>

---

<details>
  <summary style="font-size:20px"><b>What if i want artefact to go (somewhere like S3)</b></summary><br>

You can so long as the runner image has aws cli and your S3 bucket allows access.

</details>

---

<details>
  <summary style="font-size:20px"><b>Why the unit test artefact raw is not downloadable? </b></summary><br>

Need artefact:path to be defined

</details>

---

<details>
  <summary style="font-size:20px"><b>Are we offering windows runners to run .NET framework / .NET Core? </b></summary><br>

Yes

</details>

---

<details>
  <summary style="font-size:20px"><b>Is there a maximum job timeout? </b></summary><br>

There is a project settings for runner timeout. Defaults to 1h, maximum at 1 month says documentation. But all these are still subjected to overall runner setting of 1hr timeout regardless.
</details>

---

<details>
  <summary style="font-size:20px"><b>How did you get secrets from AWS? </b></summary><br>

Set up IDP and define role to give access to secrets and configure trust relationship to trust your gitlab project. See: https://docs.gitlab.com/ee/ci/cloud_services/aws/#configure-a-role-and-trust

</details>

---

<details>
  <summary style="font-size:20px"><b>How to write the trust relationship? </b></summary><br>

See docs at: https://docs.gitlab.com/ee/ci/cloud_services/aws/

</details>

---

<details>
  <summary style="font-size:20px"><b>What if my repo is a few gigs? </b></summary><br>

Base line config limits each repo to 2G. Gitlab repositories are code repositories, it is recommended that it does not store binaries like executables, pictures, or videos, etc.

</details>

---

<details>
  <summary style="font-size:20px"><b>Why my GSIB can hit SHIP-HATS GitLab but cannot git clone? </b></summary><br>

GitLab dedicated works on the SIS browser but not on the CLI, it will fail because it cannot reach a DNS that can resolve the GitLab dedicated domain. You need to check with your agency IT team to see if there could be firewall blocking for CLI.

</details>

---

<details>
  <summary style="font-size:20px"><b>How to run integration tests against my intranet service?</b></summary><br>

For intranet deployment, you need to self host runner in intranet to do integration tests against ur intranet service by providing the right network access.

</details>

---


<details>
  <summary style="font-size:20px"><b>Can I embed SHIP confluence link to Gitlab wiki? </b></summary><br>

Yes. Viewers of the wiki page have to have access to your confluence link in order to route there.
</details>

---

<details>
  <summary style="font-size:20px"><b>Will compliance framework updates break my pipeline?</b></summary><br>

We are working on compliance version release management. You will be able to upgrade at your own convenience by changing the version to reference.
</details>

---

<details>
  <summary style="font-size:20px"><b>Do we need to pay extra to use Wiki, issues tracker in Gitlab? </b></summary><br>

No. All inclusive.
</details>

---

<details>
  <summary style="font-size:20px"><b>Is Gitlab dedicated to each agency? </b></summary><br>

No. It is a shared model where all onboarded agencies will be on the same platform.
</details>

---

<details>
  <summary style="font-size:20px"><b>Can I get web app to use on my own for the next few days? </b></summary><br>


</details>

---

<details>
  <summary style="font-size:20px"><b>Can we use self-hosted runners? </b></summary><br>

It is safe to use the shared runners provided by SHIP-HATS team if agencies’ deployment environment is accessible by the runners (i.e. GCC AWS). Depends on agencies’ use cases, they can choose to use their self-hosted runners by setting them up: https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/gitlab-runners

</details>

---

<details>
  <summary style="font-size:20px"><b>What does the “ref” for inclusion of project in pipeline refer to? Will it break my pipeline if there were changes to “main” for SHIP-HATS Templates if I am including the templates in my project? </b></summary><br>

It refers to the branch of the repository that the templates were in. You may choose to reference with versioned tags instead of main branch to ensure that changes in the main branch will not affect the templates you are referencing.

</details>

---

<details>
  <summary style="font-size:20px"><b>Is there a role based access that can be configured for project? </b></summary><br>

The roles and permissions can be found here: https://docs.gitlab.com/ee/user/permissions.html. Additional changes such as restricting certain groups/users to merge a merge request or push commit on protected branch and merge request approval can be configured in project settings.

</details>

---

<details>
  <summary style="font-size:20px"><b>Can developer receive email when pipeline fails. Can logs be included in the email? </b></summary><br>

The failed pipeline email notification will be sent to the author of the pipeline: https://docs.gitlab.com/ee/user/profile/notifications.html#notification-events-on-issues-merge-requests-and-epics. Users who have access to GitLab dedicated will be using default global notification settings and the email notification can be configured: https://docs.gitlab.com/ee/user/profile/notifications.html. It is not advisable to include logs in pipeline failure email, the user is recommended to access the GitLab job to view the logs instead.

</details>

---

<details>
  <summary style="font-size:20px"><b>How powerful is the shared runners? Example: what’s the storage and ram? </b></summary><br>

Default runner (CStack runner) has 40GB and 2vCPU and 8GB mem. Docker machine is t3.medium. Agencies may setup their own self-hosted runners, if they require a different settings.

</details>

---

<details>
  <summary style="font-size:20px"><b>Who assign the roles for the project members? Is there documentation to configure this? </b></summary><br>

The owner (i.e. PA) can configure and assign roles for his/her own project members: https://docs.gitlab.com/ee/user/project/members/#add-users-to-a-project.

</details>

---

<details>
  <summary style="font-size:20px"><b>Is it possible to trigger email when there is a commit to the repository? </b></summary><br>

It can be configured using email on push integration: https://docs.gitlab.com/ee/user/project/integrations/emails_on_push.html.

</details>

---

<details>
  <summary style="font-size:20px"><b>What will be the cost for using runners? </b></summary><br>

There is no additional cost for using shared runners. There is charges for VPC connection endpoint (AWS cost) and the cost for hosting your own runners (i.e. EC2).
</details>

---

<details>
  <summary style="font-size:20px"><b>Can I build my own custom image? </b></summary><br>

You can build and store your custom image in your GitLab Project container registry. You can also contribute your custom image to the Pipeline COE (innersource).

</details>

---

<details>
  <summary style="font-size:20px"><b>Can my subsequent pipeline use the artifacts from previous pipeline under the same project? </b></summary><br>

You will need to define needs:project in a job of your subsequent pipeline. In this case, you will need to have different branch (i.e. main branch for subsequent pipeline and branch-A for previous pipeline), the documentation can be found here: https://docs.gitlab.com/ee/ci/yaml/#needsproject.

</details>

---

<details>
  <summary style="font-size:20px"><b>Can my Confi system be onboarded to SHIP-HATS 2.0 ? </b></summary><br>

Do note that:

- SHIP-HATS does not store your production transactional data.
- SHIP-HATS only store your source codes, configurations files.
- SHIP-HATS will only run a transient instance of your application (without production data and only assessable within ship-hats)
for security scanning and automated functional testing activities.

A possible way ahead for your Confi systems to be on SHIP-HATS 2.0

1. Classify your source codes as Confi(cloud) or below
    - this will not change your total system classification as it will remain as Confi
    - there is no need to re-classify any other system components e.g.(transactional Data)
1. With only your source code classified as Confi(cloud) you could leverage on SHIP-Hats for your CI/CD needs.

</details>

---


## TechPass FAQs

[TechPass FAQs](./techpass-faqs.md ':include')


### Related Topics

- [Subscription FAQs](subscription?id=faqs)




<!--
- [TechPass FAQs](techpass-faqs)
- [SEED FAQs](seed-faqs)
- [Support FAQs](support)
-->

<!--<details>
  <summary><b>How do I reset my password?</b></summary><br>
Refer to the [Reset password](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/users-self-help) section in the [SHIP-HATS portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/) documentation.
</details>
<br>-->
<!--<details>
  <summary><b>How do I reset my 2FA?</b></summary><br>
Refer to the [reset 2FA](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/users-self-help) section in the [SHIP-HATS portal](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/) documentation.
</details>
<br>-->
<!--<details>
  <summary><b>What if I have lost my mobile device?</b></summary><br>
Refer to the [manage accounts](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/#/manage-account) section to reset your account.
</details>
<br>-->
<!--<details>
  <summary><b><b>Can I access SHIP-HATS tools via GSIB device?</b></b></summary><br>
Yes. You can access SHIP-HATS tools such as Confluence, Jira, Nexus Repo, Nexus IQ, and SHIP-HATS Service Desk via GSIB.</details><br>-->
<!--
## General FAQs

>**Tip:** Click the question or triangle to view the answer.

<details>
  <summary><b>What is a named user?</b></summary><br>

A named user refers to the license that is bound to a specific user. Each named user uses a license in the subscription quota.
</details>


---

<details>
  <summary><b>Are admin accounts such as Subscription Admin (SA) and Service Accounts considered as a named user account? </b></summary><br>

Yes. Subscription Admin (SA) and Service Accounts are considered as a named user account.
</details>

---

## SEED FAQs

[SEED FAQs](./seed-faqs.md ':include')

## TechPass FAQs
-->