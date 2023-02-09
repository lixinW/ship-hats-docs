In SHIP-HATS 2.0 platform, there are 2 types of runners:  

### 1. SHIP-HATS Shared Runners

The shared runners are hosted by the SHIP-HATS team. There are 4 variants in the shared runner pool. These runners are easily accessible to users and are scalable on demand.


|Runner|Executor|Tags|Privileged|Cache Enabled|Run Untag|Version|Notes|
|---|---|---|---|---|---|---|---|
|CStack Runner|kubernetes|cstack<br>non_privileged<br>no_root|FALSE|YES|YES|NA|Run as non-root<br>run as 65533 user.
|Docker Runner|docker + machine|ship_docker<br>non_privileged|FALSE|YES|NO|NA|Run as root<br><br>We have removed privileged access for SHIP-HATS shared runner. This affects build of systems that used the shared runners with docker-in-docker. Alternatively, you can use [Kaniko](#docker-alternative-faqs).
|[Windows Runner](#windows-runner)|shell|ship_windows|N/A|YES|NO|- OS: MS Windows Server 2019 Base<br>- Git: 2.36.1<br>- Visual Studio 2022 version 17.0<br>- .Net framework 4.8 development tools| Refer to [Windows Runners](#windows-runner) for  **Libraries** and important details on **cleanup job** included with Windows Runner.
|GitLab Shared Runner on SaaS|-|-|-|-|-|-|The GitLab shared runner on SaaS may replace the above runners when available in the future. 

### 2. Self-hosted Remote Runners

The agency-hosted remote runners are the dedicated machines that are set-up and managed by agencies. These runners can connect to SHIP-HATS via the *IPSec tunnel* or *VPC endpoint* if they are hosted on GCC AWS or CC AWS. 

<!--- **GitLab Shared Runner on SaaS:** The GitLab shared runner on SaaS will be available over the next couple months. -->

For more information, refer to the [GitLab Runner](https://docs.gitlab.com/runner/) documentation.