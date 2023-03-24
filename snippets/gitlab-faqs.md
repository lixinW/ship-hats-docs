?>**Tip:** Click the triangle to view the answer.


<details>
  <summary style="font-size:20px"><b>How can team do a Docker Image push to AWS ECR with Shared Runner? Is there a template for this requirement?	</b></summary><br>

Refer to the [COE template for Awscli Docker Image](https://sgts.gitlab-dedicated.com/pipeline-coe/awscli-docker-image).

</details>

---

<details>
  <summary style="font-size:20px"><b>I am receiving an error <i>Cannot connect to the Docker daemon at unix:///var/run/docker.sock. for docker build cmd.</i>. What can I do? </b></summary><br>

Consider using [ship-hats-templates](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates) to overcome these errors.

Refer to [Common Functions](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/blob/main/templates/.gitlab-ci-common.yml) in GitLab. 

</details>

---

<details>
  <summary style="font-size:20px"><b>Any tool provided to convert Bamboo to GitLab yaml? </b></summary><br>

No, we do not have any tools to convert Bamboo to GitLab yaml. The team is working on streamlining Bamboo pipelines to GitLab yaml. You can access the [E2E templates](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates) to apply.

</details>

---

<details>
  <summary style="font-size:20px"><b>Who can assign the roles for the GitLab project members? Is there documentation to configure this? </b></summary><br>

The owner (i.e. Project Admin) can configure and assign roles for their own project members. For more details, refer to [GitLab documentation](https://docs.gitlab.com/ee/user/project/members/#add-users-to-a-project).
</details>

---

<details>
  <summary style="font-size:20px"><b> Currently developers with Developer role unable to see Merge button. How do I enable this without setting the role to Maintainer?		</b></summary><br>

In GitLab, navigate to your project > **Settings**/**Repository** to make the necessary changes.

</details>

---

<details>
  <summary style="font-size:20px"><b>Will the GitLab Pages feature be available in SHIP-HATS 2.0? </b></summary><br>

Yes, GitLab Pages feature is in SHIP-HATS 2.0 roadmap. It is tentatively planned for Q1 2023. 
</details>

---

<details>
  <summary style="font-size:20px"><b>How to update GitLab project and Subgroup settings configurations as code? For example, Adding members, their roles, and other project and group level settings.	</b></summary><br>

Refer to following documentation resources:
- [https://registry.terraform.io/providers/gitlabhq/gitlab/latest/docs](https://registry.terraform.io/providers/gitlabhq/gitlab/latest/docs)
- [https://docs.gitlab.com/ee/user/project/code_owners.html](https://docs.gitlab.com/ee/user/project/code_owners.html)
</details>

---

<details>
  <summary style="font-size:20px"><b> Can I use Auto DevOps with SHIP-HATS 2.0?</b></summary><br>

Yes, Auto DevOps is available. However, we encourage you to explore our E2E templates. You can access the [E2E templates](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates).

</details>

---

<details>
  <summary style="font-size:20px"><b>What if I want artefact to go (somewhere like S3)</b></summary><br>

You can do so if the runner image has AWS CLI and your S3 bucket allows access.
</details>

---

<details>
  <summary style="font-size:20px"><b>Why the unit test artefact raw is not downloadable? </b></summary><br>

Make sure that `Need artefact:path` is defined.

</details>

---

<details>
  <summary style="font-size:20px"><b>How can I get secrets from AWS? </b></summary><br>

1. Set up IDP and define role to give access to secrets.
1. Configure trust relationship to trust your gitlab project. 
1. Refer to [GitLab documentation](https://docs.gitlab.com/ee/ci/cloud_services/aws/#configure-a-role-and-trust).

</details>

---

<details>
  <summary style="font-size:20px"><b>How to write the trust relationship? </b></summary><br>

Refer to [GitLab documentation](https://docs.gitlab.com/ee/ci/cloud_services/aws/). 

</details>

---

<details>
  <summary style="font-size:20px"><b>What if my repo is a few GB? </b></summary><br>

Baseline configuration limits each repo size to 2G. GitLab repositories are code repositories. Therefore, it is recommended that it does not store binaries like executables, pictures, or videos, etc. 

If your GitLab repo size > 2GB repo, consider reducing size. For further support, [raise a service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) with your requirement.
</details>

---

<details>
  <summary style="font-size:20px"><b>Why my GSIB can hit SHIP-HATS GitLab but cannot git clone? </b></summary><br>

GitLab dedicated works on the SIS browser but not on the CLI. It will fail because it cannot reach a DNS that can resolve the GitLab dedicated domain. You need to check with your agency IT team to see if there could be firewall blocking the CLI.
</details>

---

<details>
  <summary style="font-size:20px"><b>Can I embed SHIP-HATS Confluence link to GitLab wiki? </b></summary><br>

Yes. Viewers of the GitLab wiki page must have access to your Confluence link to route from GitLab to Confluence.
</details>

---

<details>
  <summary style="font-size:20px"><b>Will compliance framework updates break my pipeline?</b></summary><br>

We are working on compliance version release management. You will be able to upgrade at your own convenience by changing the version to reference. [Compliance Framework](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/compliance-framework)
</details>

---

<details>
  <summary style="font-size:20px"><b>Do we need to pay extra to use Wiki or Issues tracker in GitLab? </b></summary><br>

No. 
</details>

---

<details>
  <summary style="font-size:20px"><b>Is GitLab dedicated to each agency? </b></summary><br>

No. It is a shared model where all onboarded agencies will be on the same platform.
</details>

---

<details>
  <summary style="font-size:20px"><b>What does the “ref” for inclusion of project in pipeline refer to? Will it break my pipeline if there were changes to “main” for SHIP-HATS Templates if I am including the templates in my project? </b></summary><br>

It refers to the branch of the repository that the templates were in. You may choose to reference with versioned tags instead of main branch to ensure that changes in the main branch will not affect the templates you are referencing.
</details>

---

<details>
  <summary style="font-size:20px"><b>Is there a role based access that can be configured for project in GitLab? </b></summary><br>

Refer to [GitLab roles and permissions documentation](https://docs.gitlab.com/ee/user/permissions.html). You can configure Project Settings in GitLab for additional changes such as restricting certain groups/users to merge a merge request or push commit on protected branch and merge request approval.
</details>

---

<details>
  <summary style="font-size:20px"><b>Can developer receive email when pipeline fails. Can logs be included in the email? </b></summary><br>

The failed pipeline email notification will be sent to the author of the pipeline. Refer to [GitLab documentation](https://docs.gitlab.com/ee/user/profile/notifications.html#notification-events-on-issues-merge-requests-and-epics). 

If you have access to GitLab dedicated, you will be using default Global Notification settings. You can [configure the email notification](https://docs.gitlab.com/ee/user/profile/notifications.html). It is not advisable to include logs in pipeline failure email. We recommend that you access the GitLab job to view the logs.
</details>

---

<details>
  <summary style="font-size:20px"><b>Is it possible to trigger email when there is a commit to the repository? </b></summary><br>

You can [enable emails on push](https://docs.gitlab.com/ee/user/project/integrations/emails_on_push.html) to receive email notifications for every change that is pushed to your project.

</details>

---

<details>
  <summary style="font-size:20px"><b>Can I build my own custom image? </b></summary><br>

You can build and store your custom image in your GitLab Project container registry. You can also contribute your custom image to the [Pipeline COE (innersource)](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/pipeline-coe).

</details>

---

<details>
  <summary style="font-size:20px"><b>Can my subsequent pipeline use the artifacts from previous pipeline under the same project? </b></summary><br>

You will need to define `needs:project` in a job of your subsequent pipeline. In this case, you will need to have different branch (i.e. main branch for subsequent pipeline and branch-A for previous pipeline). Refer to [GitLab documentation](https://docs.gitlab.com/ee/ci/yaml/#needsproject).

</details>

---

<details>
  <summary style="font-size:20px"><b> Can I access SHIP-HATS source code repository via a non-SE GSIB?</b></summary><br>

You could view the source codes via a non-SE GSIB and edit files via the GitLab Web IDE using secure browsing. However, you will not be able to perform most development activities on a non-SE GSIB, such as `git push`, `git pull`, `git fetch` in SHIP-HATS.

</details>

---

<details>
  <summary style="font-size:20px"><b>How to support service accounts that are not tied to a human, no TechPass and SEED for the purpose of automating updating git tags, scheduled pipelines owner, etc.?	</b></summary><br>

We recommend that you use auto-generated CI tokens for all the tools need. This feature is available via the SHIP-HATS portal. You can [retrieve these CI tokens](https://docs.developer.tech.gov.sg/docs/ship-hats-portal/manage-tokens) and update them in your pipelines.	
</details>

---
