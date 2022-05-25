# SHIP-HATS Terms and Policies

**Topics**
- [Announcements](#announcements)
- [Service Level Agreement](#service-level-agreement)
- [Third Party Schedule](#third-party-schedule)
- [Cleanup Policy](#cleanup-policy)
- [Plugin Review Process]()

## Announcements

The policies and annoucements below have been emailed out to SHIP-HATS users. It is cross posted here for ease of use.

### 25 Oct 2021

In the view of improving our service capability and operation efficiency, SHIP-HATS will be performing phase-1 Bamboo plans clean-up activities by deleting suspended or disabled plans (older than a year ago). Additionally,  we will contact high usage tenants separately to assist them on Plan expiry configurations and housekeeping settings.

We seek your help to housekeep the older plans at your end. On 10th Nov, 2021, disabled plans older than 1 year will be deleted.  As we continually seek to improve our solutions, we encourage you to refer to the [Bamboo Plans - Housekeep best practices](https://confluence.ship.gov.sg/display/SHIP/Bamboo+clean+up+and+best+practices) confluence page for more details.   

Agencies are requested **not** to override the default SHIP-HATS Bamboo Plan configuration for any of your plans. Please contact us if you require any exemption or support from us.  


### FAQs
- **What if I want to keep one or few of disabled plans for our future reference?**

  We strongly recommend you to maintain them at your local environment. However, you can still change the configuration at SHIP-HATS Bamboo system by updating the plan from disabled to enable state.

- **Will there be any notification send to agency what are all the disabled plans were terminated?**

  No notification will be sent to the agency. Please work with your Project Admin and complete the required maintenance actions.

- **Which resources will be removed by deleting the suspended or disabled plans?**
  
  Deleting a plan completely removes the plan from SHIP-HATS Bamboo system. In addition, deleting a plan deletes the corresponding branch plans from Bamboo. Kindly review all your disabled or suspended plans and contact us if you have any concern before 10th Nov, 2021.
  
  >**Note:** If your source code is configured in Bitbucket repo and branch, there will be no impact to these linked bitbucket repos.

- **I have bamboo plans configured in SHIP-HATS. Can I delete or manage the plans by myself?**

  Yes. Users with **Admin** permission to the project plans can delete or manage the plans. For further guidance, please work with the Project Admin for your requirement.

- **Do you have any recommended Bamboo Plan configurations for SHIP-HATS plans?**
  
  Tenants are expected not to keep more than 10 last builds per plan. After successful build, the plan resources (eg, artifacts, build logs) expiry should keep as minimal as possible. Our default recommended expiry is after 3 days of build and release artifacts.

<!--
<details>
 <summary><b>What if I want to keep one or few of disabled plans for our future reference?</b></summary><br />
 We strongly recommend you to housekeep them at your local environment. However, you can still change the configuration at SHIP-HATS Bamboo system by updating the plan from disabled to enable state.
</details>
<br >
<details>
 <summary><b>Will there be any notification send to agency what are all the disabled plans were terminated?</b></summary><br>
No notification will be sent to the agency. Please work with your Project Admin and complete the required housekeeping actions.
</details>
<br >

<details>
 <summary><b>Which resources will be removed by deleting the suspended or disabled plans?</b></summary><br>
Deleting a plan completely removes the plan from SHIP-HATS Bamboo system. In addition, deleting a plan deletes the corresponding branch plans from Bamboo. Kindly review all your disabled or suspended plans and contact us if you have any concern before 10th Nov, 2021.  

<br >
<b>Note:</b> If your source code is configured in Bitbucket repo and branch, there will be no impact to these linked bitbucket repos. 


</details>
<br >

<details>
 <summary><b>I have bamboo plans configured in SHIP-HATS. Can I delete or manage the plans by myself?</b></summary><br>
Yes. Users with <b>Admin</b> permission to the project plans can delete or manage the plans. For further guidance, please work with the Project Admin for your requirement.
</details>
<br >

<details>
 <summary><b>Do you have any recommended Bamboo Plan configurations for SHIP-HATS plans?</b></summary><br>
Tenants are expected not to keep more than 10 last builds per plan. After successful build, the plan resources (eg, artifacts, build logs) expiry should keep as minimal as possible. Our default recommended expiry is after 3 days of build and release artifacts.
</details>
<br >
-->



<!--
<details>
 <summary> 25 Oct 2021</summary><br>
 
 
In the view of improving our service capability and operation efficiency, SHIP-HATS will be performing phase-1 Bamboo plans clean-up activities by deleting suspended or disabled plans (older than a year ago). Additionally,  we will contact high usage tenants separately to assist them on Plan expiry configurations and housekeeping settings.

We seek your help to housekeep the older plans at your end. On 10th Nov ‘21,  disabled plans older than 1 year will be deleted.  As we continually seek to improve our solutions, we encourage you to refer to the [Bamboo Plans - Housekeep best practices](https://confluence.ship.gov.sg/display/SHIP/Bamboo+clean+up+and+best+practices) – the confluence page documentation with more details.   

 
#### FAQs

**1. What if I want to keep one or few of disabled plans for our future reference?**
We strongly recommend you to housekeep them at your local environment. However you can still change the configuration at SHIP-HATS Bamboo system by updating the plan from disabled to enable state.

**2. Will there be any notification send to agency what are all the disabled plans were terminated?**
No notification will be sent to the agency. Please work with your project admin and do necessary housekeeping actions.

**3.What are all the resources will be removed by deleting the suspended or disabled plans?**
Deleting a plan completely removes from SHIP-HATS Bamboo system. FYI deleting a plan also delete its branch plans from Bamboo. [Note: If your source code(s) configured in Bitbucket repo and branch, no impact to these linked bitbucket repos]. Kindly review all your disabled / suspended plans and contact us if you have any concern before 10th Nov ‘21.

**4. I have bamboo plans configured in SHIP-HATS; Am I able to delete or housekeep the plans by myself?**
Yes. Users with “Admin” permission to the project plans; able to perform Delete Plan action. If not, please work with the Project admin for the requested.
Do you have any recommended Bamboo Plan configurations for SHIP-HATS plans?
Tenants are expected not to keep more than 10 last builds per plan. After successful build, the plan resources (eg, artifacts, build logs) expiry should keep as minimal as possible. Our default recommended expiry is after 3 days of build and release artifacts.
 

Agencies are reminded NOT to override the default SHIP-HATS Bamboo Plan configuration for any of your plans. Please contact us if you need any exemption or assist from us.  
 
  </details>
 -->
<details>
 <summary> 24 Sep 2021 </summary><br>
 

SHIP-HATS will be adding a clean-up policy to the Nexus Repositories to remove old binary repos and artifacts published 6 months ago, which will take effect from 11th Oct 2021.  This Policy is aimed at service maintenance and performance improvement. 

From 11th Oct ‘21 onwards, older artifacts in your nexus repositories will be deleted automatically without any notification. We request agencies to do periodical review of repositories and large blobstores and housekeep them at your end.  As we continually seek to improve our solutions, we encourage you to refer to the [Nexus Repository - Cleanup Policies](https://help.sonatype.com/repomanager3/repository-management/cleanup-policies) – the Sonatype documentation with more details. 

Questions? 

For further queries, please contact SHIP-HATS Operation support via email at enquiries_ship@tech.gov.sg, and if you have any feedback on product improvements, feel free to let us know at https://go.gov.sg/she.



#### FAQs

**1. How to check which repositories are using the most space?**

Please contact your repo administrator to have a check on this.   

**2. Will there be any notification send to agency when the older artifacts are purged?**

No notification will be sent to the agency. Please do periodical review and do necessary housekeeping of Repos, images and artifacts at your end. Do contact us if you require any support.

  </details>


<details>
 <summary> 6 Sep 2021 </summary><br>

SHIP-HATS will be implementing an Authenticated Request Limits (Throttling Policy) to Bitbucket service for all tenants, which will take effect from 15th  Sep 2021. This Policy is aimed at improving service stability and performance improvement.

In the view of recent utilization of bitbucket usage patterns, a token bucket algorithm will be introduced to bitbucket users consuming the services. As we continually seek to improve our solutions, we encourage you to refer to the Bitbucket Rate Limiting – the Atlassian documentation with more details.  

**Bitbucket Rate Limiting Policy**

Find below the guideline for tenants with this Rate limiting setting turned ON.
| **Guideline** | **Action Required** |
| -- | -- |
| 1. From 15 Sep ‘21 onwards, Rate limiting will be imposed and token bucket size and token bucket fill rate configured with the default settings.  | Review your build plans and requests regularly. If you are receiving returned error code 429 (ie when too many requests in a given amount of time);  look for the below options to mitigate the impact of rate-limiting </br> - Suggest users to review their code/scripts that the requests are not made in large bursts. </br> - Spread your requests. Use multiple users and split repos to perform the request rather than stick with one user. </br> - Cache API calls for at least a few seconds, and try to avoid making repetitive API calls. </br> - Avoid tight loops by writing scripts that wait for each REST request to finish before a new one is fired.</br>If any of the above doesn’t help, reach out to us SHIP-HATS Service Desk for further advice. |
| 2. Agencies with reasonable bitbucket requests as standard operational. | Nil |
| 3. Agencies are reminded NOT to perform load test or massive requests. | Nil. You will be receiving 429 returned error if your requests exceeded the rate limit configured and do necessary mitigation |

Questions?

For further queries, please contact SHIP-HATS Operation support via email at enquiries_ship@tech.gov.sg, and if you have any feedback on product improvements, feel free to let us know at https://go.gov.sg/she.



**FAQs**

**1. Where and how can we see request counts on our Bitbucket requests (eg. Git, SSH, Push/Pull commits)?**

There is currently no way for end-users to check this. If you experience any issues due to any integration of plugins or tools, contact SHIP-HATS Service Desk team to assess and advise on it.  

**2. Will there be any notification send to agency when rate limit is exceeded?**

No notification will be sent for termination. Please monitor your build plans and responses received on the requests at your end.

**3. Shall I request to increase the rate limit?**

SHIP-HATS will not recommend to increase the rate limit which will have an impact to system stability and performance. Perhaps you may try out the possible mitigation options shared above to reduce the impact. You can reach out to us to assess your use cases and suggest further.  Kindly note that we will assess the need on a case-by-case basis.

 </details>
 
<details>
 <summary> 19 July 2021</summary><br>


SHIP-HATS will be implementing a Fair Usage Policy for the use of Bamboo Elastic Agents, which will take effect from 1st Aug 2021. This Policy is aimed at improving the developer experience so that all our users can run their Bamboo plans in a timely manner.

**Feedback on Bamboo Agent Utilisation**

We reviewed feedback that we have received through various channels such as the DevSatisfaction Survey, and via service tickets that you have raised. We found that common feedback centered around the unavailability of bamboo agents. Since then, we have been monitoring the bamboo agent usage patterns and have been able to work with some of you to spread out your jobs so that most jobs can be picked up quickly. In addition, we have put in place some monitoring tools to centrally monitor bamboo agent utilisation on a regular basis.

**New Fair Usage Policy**

To further reduce bamboo agent waiting times, we are putting in place a Fair Usage Policy with the following guidelines:

| **Guideline** | **Action Required** |
| -- | -- |
| From 1 Aug ‘21 onwards, in order to free up resources for the next build, builds taking more than 500 minutes will be terminated automatically without any notification. | Review build plans regularly and reach out to the Service Desk for any specific use-cases that require more than 500 minutes.  We will assess the need on a case-by-case basis. |
|  2. Agencies are recommended to run jobs in their own CI/CD pipeline, only schedule jobs when necessary during low peak hours. | Nil |
|  3. Agencies are reminded NOT to perform load tests using elastic bamboo agents. | Nil |

As we continually seek to improve our solutions, we encourage you to refer to the confluence page, [Bamboo Elastic Agents – Fair Usage guideline](https://confluence.ship.gov.sg/display/SHIP/Bamboo+elastic+agents+-+fair+usage+guideline) for the **latest** Fair Usage Policy guidelines.

**Questions?**

For further queries, please contact SHIP-HATS Operation support via email at enquiries_ship@tech.gov.sg, and if you have any feedback on product improvements, feel free to let us know at https://go.gov.sg/she.

**FAQs**

**1. We have a scheduled build plan running every month for about 8-9hrs. Can I request for exemption?**

Drop an email to enquiries_ship@tech.gov.sg with more details. Our team will evaluate and advise.

**2. Will there be any notification send to the agency when the build plan is terminated?**

No notification will be sent for termination. Please monitor your build plans regularly and contact us if you require any support.

 </details>
 
<details>
 <summary>  27 May 2020 </summary><br>

As part of our security best practices, please be informed that SHIP will accept VPC endpoint acceptance requests only from GCC Restricted AWS accounts. Service consumers must adhere below the terms and conditions when submitting the VPC end point request to SHIP Service Desk. 

Support request should be raised in SHIP Service Desk by respective project admin (or approved by respective project admin).
Agency should use only **programmatic access** for any VPC end point services connecting with SHIP services.
For non-Restricted accounts; service consumer must seek approval from SHIP team for any new VPC end point requests.  
FYI. New clause will be added in upcoming SHIP Service Agreement which should be formally approved by the agency. For existing approved accounts, SHIP team will make an assessment reach out tenant(s) if required.

Drop us a note if you require any clarifications on this matter.

  </details>

## Service Level Agreement
This Service Level Agreement, henceforth also known as “SLA” is between Government
Technology Agency (GovTech/Service Provider) and the client for all services and service
levels in connection to SHIP-HATS, henceforth also known as “Service”.

During the period of the Subscription Term, GovTech will provide:
1. System Availability of at least 98.0% availability per service/ application, inclusive of
scheduled maintenance downtime.
2. Technical support to resolve any errors in the Services, in accordance with the following
error resolution schedule. Please see table below.
3. Monthly maintenance and updates (including patches) will be notified 5 days in advance.

| Severity Level | Description | Resolution time |
| :------------- | :---------- | :-------------- |
| 1 | Critical incident that prevents use of all Services | 1 to 3 business days |
| 2 | Incident that disables major functions of the Services. | 4 to 6 business days |
| 3 | Incident that disables minor functions. |Subject to complexity of the error in the service |

| Terms | Description |
| :--- | :----------- |
| Resolution Time | Time required to provide a permanent or temporary solution in respect of the relevant error and commences from the time GovTech is notified of the error. |

Classification of the severity levels is subject to GovTech&#39;s reasonable discretion. Technical
support hours are Mondays to Fridays 9.00 am to 5.30 pm except public holidays. If the solution
is temporary, GovTech will continue to work on the issue until a permanent solution is found.

## Third Party Schedule 

All applicable terms and conditions relating to the following: 
1. Atlassian Service / Data Center Products - https://www.atlassian.com/legal/privacy-policy/product-family 
2. OpenVPN - https://openvpn.net/terms  & https://openvpn.net/license 

## Cleanup Policy

This section provides an overview about SHIP-HATS cleanup policy for your Nexus Repositories and recommendations that you can follow to improve performance and maintenance.

### Audience

SHIP-HATS users.

### Why do we need a cleanup policy?

A cleanup policy helps to purge unnecessary components to optimise disk space supporting better performance. SHIP-HATS leverages upon [Sonatype's Cleanup feature](https://help.sonatype.com/repomanager3/repository-management/cleanup-policies) to manage components at repository level.

### SHIP-HATS cleanup policy

Our default cleanup policy is configured to automatically delete a component from your nexus repository after 180 days from the date of its creation. Our cleanup policy is at repository level and not at subscription/billing account level.

This policy is applied to your repositories from October 11 2021, and the task is scheduled to run daily at 01.00 AM.

We highly recommend you to periodically review your repositories and to housekeep them from your end.

### FAQs

- **Will there be any customer impact when the cleanup task is running?**

   No, there will be no customer impact.

- **What should I do if I wish to retain some of my artifacts of a repository beyond 180 days?**

   Raise a service request to SHIP-HATS with your requirements.

- **Can I have my own cleanup policy?**

   Yes. Raise a service request to SHIP-HATS with your requirements.

- **How to check which of our repositories are using the maximum space?**

   Contact your repo administrator to get this information.

- **Will there be any communications sent to agencies for the cleanups?**

   There was an initial communication sent to our tenants on September 24, 2021 about SHIP-HATS cleanup policy. As this is a recurring task scheduled every day at   01:00 AM, there will be no ongoing communications.
