## About Runners

Runners **run the CI/CD pipelines**. The Pipeline **jobs are assigned** to available Runners. Runners **execute the work** you define in your GitLab pipeline jobs.

You can **install Runners** on your local machine, VM, Docker container, or any cloud infrastructure.

Runners are **supported on** Linux, Windows, MacOS, and FreeBSD.

### GitLab Runner Executor

GitLab Runner Executor **determines the environment** in which a job will run: 
- VM via a hypervisor such as VirtualBox
- Shell
- Remote SSH
- Docker
- Kubernetes
- Custom executor

### GitLab Tags

You can **configure Tags** on the GitLab Runner. **Reference tags** in a GitLab pipeline **specify which runners should be used for the job**. An example is shown in the image below:

![Tags](./images/runner-tags.png ':size=40%')


## Types of Runners

In SHIP-HATS 2.0 platform, there are 2 types of runners:  

- [SHIP-HATS Shared Runners](#ship-hats-shared-runners)
- [Self-hosted Remote Runners](#self-hosted-remote-runners)

<!--
|SHIP-HATS Shared Runners|Self-hosted Remote Runners|
|---|---|
|- Hosted by SHIP-HATS team <br><br>- Created on-demand <br><br>- No overheads for Agencies as they do not need to maintain runners<br><br>- Available for all SHIP-HATS users at no additional costs!|- Dedicated machines that are set-up and managed by agencies<br><br>- Can be configured for Group or Project level access<br><br>- Can connect to SHIP-HATS via the *IPSec tunnel* or *VPC endpoint* if they are hosted on GCC AWS or CC AWS<br><br>- Agencies bear the costs of hosting their own runners<br><br>- Agencies have full-control of the runners
-->

## SHIP-HATS Shared Runners
<!--The shared runners are hosted by the SHIP-HATS team. There are 4 variants in the shared runner pool. These runners are easily accessible to users and are scalable on demand.-->

SHIP-HATS Shared runners are: 
- Hosted by SHIP-HATS team 
- Created on-demand 
- Available for all SHIP-HATS users at no additional costs!
- No overheads for Agencies as they do not need to maintain runners

There are 4 variants: 

|Runner|Executor|Tags|Privileged|Cache Enabled|Run Untag|Egress IP Address|
|---|---|---|---|---|---|---|
|[CStack Runner](#cstack-runner)|kubernetes|cstack<br>non_privileged<br>no_root|FALSE|YES|YES|13.251.177.7/32<br>18.143.61.190/32
|[Docker Runner](#docker-runner)|docker + machine|ship_docker<br>non_privileged|FALSE|YES|NO|18.143.26.175/32<br>18.142.30.19/32<br>18.140.93.144/32
|[Windows Runner](#windows-runner)|shell|ship_windows|N/A|YES|NO|18.143.26.175/32<br>18.142.30.19/32<br>18.140.93.144/32
|GitLab Shared Runner on SaaS||The GitLab shared runner on SaaS may replace the above runners when available in the future. 

### CStack Runner

?> We **recommend** using this runner by default.

- Run as non-root
- Run as 65533 user
- Uses [Container Stack](https://go.gov.sg/container-stack-docs) in SGTS

|Runner|Executor|Tags|Privileged|Cache Enabled|Run Untag|Version|
|---|---|---|---|---|---|---|
|CStack Runner|kubernetes|cstack<br>non_privileged<br>no_root|FALSE|YES|YES|NA|
 

### Docker Runner

?> Use this runner to **build a docker image**.

- Run as root
- This runner is slower than CStack Runner for use cases that can run both runners.
- We have removed privileged access for SHIP-HATS shared runner. This affects build of systems that used the shared runners with docker-in-docker. 
- Use [Kaniko as a docker alternative](#docker-alternative-faqs). Refer to [Build and push docker image](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-docker-buildyml) template.

|Runner|Executor|Tags|Privileged|Cache Enabled|Run Untag|Version|
|---|---|---|---|---|---|---|
|Docker Runner|docker + machine|ship_docker<br>non_privileged|FALSE|YES|NO|NA|



### Windows Runner

?> Use this runner for **.Net framework**. 

Note that a [clean up job](#note-the-following-when-using-windows-runner) is required at the beginning.

|Runner|Executor|Tags|Privileged|Cache Enabled|Run Untag|Version|
|---|---|---|---|---|---|---|
|Windows Runner|shell|ship_windows|N/A|YES|NO|- OS: MS Windows Server 2019 Base<br>- Git: 2.36.1<br>- Visual Studio 2022 version 17.0<br>- .Net framework 4.8 development tools| 

**Libraries**

|Component|Path|
|---|---|
**JAVA_HOME**|  C:\Program Files\OpenJDK\openjdk-11.0.15_10
**Git**|  C:\Program Files\Git
**MSBuild17_PATH**| C:\Program Files\Microsoft Visual Studio\2022\BuildTools\MSBuild\Current\Bin
**MSBuild16_PATH**| C:\Program Files (x86)\Microsoft Visual Studio\2019\BuildTools\MSBuild\Current\bin 
**MSBuild15_PATH**| C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools\MSBuild\Current\bin 
**.NET SDK**|C:\Windows\Microsoft.NET\Framework64\v4.0.30319 - v4 (64 bit)<br><br>C:\Windows\Microsoft.NET\Framework\v4.0.30319 -v4(32 bit)
**AppDeployment Toolkit**|C:\PADT\Toolkit
**VS2017_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2017\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**VS2019_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2019\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**VS2022_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2017\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**Microsoft VS Code**|C:\Program Files\Microsoft VS Code

**Note the following when using Windows Runner:**

- Windows Runner has been set to run one job per instance at a time. 
- Windows Runner includes a **cleanup job** to remove all the downloaded and build artefacts after the job completes. For this cleanup job to work, you must use `git clone` (instead of `git fetch`) in your.NET project settings. If you use `git fetch`, the folder becomes unremovable.
    To change the project settings, you can follow one of the following methods:
    - Go to **Settings** > **CI/CD** > **General Pipelines** > **Git strategy**, and then select **Git clone**.

    ![Git Strategy Properties](./images/git-strategy-properties.png)

    OR  
    - Enforce `git clone` in your `gitlab-ci.yml` file by setting the `GIT_Strategy` variable to: `GIT_STRATEGY: clone`

    ![Git Strategy Command Line](./images/git-strategy-cmd.png ':size=40%')

-  Since the cleanup job has been enabled in Windows Runner to clean up everything after the job completes, you must push the artefacts to their repository (e.g. Nexus) to ensure data safety.
- You must complete the necessary cleanup after the build is completed by deleting any password or confidential files that might have been created or downloaded during the build job (e.g., docker config).

## Self-hosted Remote Runners

<!--The agency-hosted remote runners are the dedicated machines that are set-up and managed by agencies. These runners can connect to SHIP-HATS via the *IPSec tunnel* or *VPC endpoint* if they are hosted on GCC AWS or CC AWS.--> 

Self-hosted Remote runners are:
- Dedicated machines that are set-up and managed by agencies
- Can be configured for Group or Project level access
- Can connect to SHIP-HATS via the *IPSec tunnel* or *VPC endpoint* if they are hosted on GCC AWS or CC AWS

For these runners: 
- Agencies bear the costs of hosting their own runners
- Agencies have full-control of the runners


## Remote Runner Registration

For Remote runner registration, Group or Project owner/maintainer can obtain runner token through the UI. Registered runner has access to the project code. Therefore, review properly when granting group/project level permission.

![Remote registration](./images/remote-registeration.png)

## Remote Runner Architecture

In the below example diagram (referenced from an [AWS DevOps Blog](https://aws.amazon.com/blogs/devops/deploy-and-manage-gitlab-runners-on-amazon-ec2/
)), you can see the use of an AWS CloudFormation template to set up a Docker-based runner on 2 different AWS account environments. This architecture also uses ASG to allow the ease of scaling up the runner. You can also attach different IAM roles/Security group to the runners according to your setup.

With this setup, the runner will easily have the required network/roles access that it needs for the build job because it is already hosted in the environment for which it requires the access.


![Remote Runner Architecture](./images/remote-runner-architecture.png)

Few additional examples are provided below for your reference. 

### Example: Azure

![Azure 1](./images/architecture-azure1.png ':size=120%')

<!--### Example 2: Azure

![Azure 2](./images/architecture-azure2.png ':size=120%')-->

### Example: AWS

![AWS 1](./images/architecture-aws1.png ':size=120%')

## Choosing a Self-hosted Remote Runner

**Determine the tasks** your self-hosted runner is running to choose whether you require a CI runner, CD runner, or CI/CD runner.

|Runner|When to choose|
|---|---|
CI runner|When you need your runner to have Internet compartment. For example, placing your runner in an Internet compartment will be usually required if your build jobs need to have access to external sources.
CD runner|When you need your runner to have access to your application. For example, your CD runner will need to have network access to your application host when you need to transport your build artifact that you have built into your application host.
CI/CD runner|When you require: Internet compartment and Access to your application as described above.|

**Ensure Recommended Runner Specifications are met**
  - t3.medium
  - Start small and adjust to your future needs


## GitLab Runner Monitoring

The GitLab runner has embedded Prometheus metrics HTTP server for monitoring.
- Runner business logic metrics 
- Go-specific process metrics (garbage collection, memory stats)
- General process metrics (memory, CPU utilization )
- Build version information

For more information, refer to the [GitLab runner monitoring](https://docs.gitlab.com/runner/monitoring/) documentation.



## Recommended Approach

- SHIP-HATS Shared  Runners is highly recommended 
- Use Remote runner for what SHIP-HATS Shared  Runners do not support (example iOS) 
- Unlike Bamboo, GitLab has a more robust runner mechanism with sufficient runners to support parallel jobs

?> To save costs, agencies should consider using the SHIP-HATS Shared  Runners except for highly urgent projects that require dedicated runners. 


## Docker Alternative FAQs

>**Tip:** Click the question or triangle to view the answer.

<details>
  <summary style="font-size:20px"><b>Is there a sample pipeline template available using Kaniko?</b></summary><br>

You can use the [Build and push docker image](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-docker-buildyml) template. This template allows you to build and push docker image to private registry in one single action which is defined in the "script" key. 

?> **Note:** This template might be updated in the future to use other docker alternatives. 
</details>

---

<details>
  <summary style="font-size:20px"><b>What docker alternatives are available to replace docker commands?</b></summary><br>

In SHIP-HATS Templates (from tag v1.0.4), the docker alternative tools used in our templates include Kaniko, Skopeo, and Crane. 
</details>

---

<details>
  <summary style="font-size:20px"><b>Why can't SHIP-HATS Templates use one tool (e.g. Buildah or Podman) to replace all docker commands? </b></summary><br>
<!--Why multiple docker alternative tools are available in SHIP-HATS Templates?-->

In our testing, Buildah and Podman require minimally some elevated capabilities on runner to work. These elevated capabilities are undesirable in a shared runner model as they allow host escape. So, SHIP-HATS Templates leverage several tools that do not require such runner settings to fulfil some docker commands. For example: 

<!--Based on the docker alternatives that we have identified and used in SHIP-HATS Templates, there isn't one tool that can replace docker commands completely. Therefore, we have included multiple docker alternatives that can perform certain operations that docker commands offer. -->

- Kaniko is able to build an image from a `Dockerfile` and push it to a registry. For example, it is ideal to replace `docker build` and `docker push` commands.
- Skopeo is known for copying an image from and to various storage mechanisms. For example, it is ideal to replace `docker tag`.
- Crane is a tool for interacting with remote images and registries. For example, it is ideal to replace `docker pull` and `docker push` (that cannot be performed by Kaniko and Skopeo).
</details>

---

<details>
  <summary style="font-size:20px"><b>Are the docker alternatives identified able to fully replace the docker commands?</b></summary><br>

No, there are certain functions that cannot be performed by the suggested docker alternatives, such as `docker run` and `docker compose`. You may consider using [GitLab services](https://docs.gitlab.com/ee/ci/services/) with your services designed to provide additional features which are network accessible.
</details>

---

<details>
  <summary style="font-size:20px"><b>Docker alternative tools are insufficient for me and I would still need to run docker commands directly. What can I do?</b></summary><br>

SHIP-HATS does not support Docker-in-Docker (`dind`) or privileged shared runners. You need to self host privileged runner to use `dind` image for running docker commands directly. Refer to [Set up GitLab Runners documentation](gitlab-runners) to set up self-hosted GitLab Runner.
</details>

---

<details>
  <summary style="font-size:20px"><b>Can the docker alternatives run on non-root and non-privileged runners (CStack runners)?</b></summary><br>

Based on our testing on docker alternatives, Skopeo and Crane can run on non-root and non-privileged runners (tags: cstacks, non_privileged, no_root) whereas Kaniko can run on runners with root and non-privileged runners (tags: ship_docker, non_privileged).
</details>

---

<details>
  <summary style="font-size:20px"><b>Are there any image or job templates that I can reference in my job if there are tasks that require multiple tools. For example, AWS assumes role with Kaniko to build and push image to AWS ECR.</b></summary><br>

[Pipeline COE](https://sgts.gitlab-dedicated.com/innersource/projects/sgts-pipelinecoe/containers) is an InnerSource project where custom images are built and shared across all projects. Most images in Pipeline COE are built from container base image that comes with multiple common tools (e.g., Wget, Git, curl, and JQ).

<!--Please note that this project is a work in progress and the location of the images might be changed later. You may refer to the images there in your job should you find any one suitable. You may refer to the images in your job to find something suitable to your requirements.--> 

If you are unable to find a suitable image in Pipeline COE, you may [raise a request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) or if you find an image that can add on the tools that you require, you may edit the Dockerfile and raise an MR for platform team to review and approve. 
</details>

---

<!--

## Remote Runner Architecture

### Manage self-hosted runners
### Configure runners 

#### Configure runners for deployment to GCC


## Choosing a runner
### When to use which runner
### Include Docker  Images with Kaniko

## Common Errors

-->