We strive to ensure consistent availability to all users and improve our service capability and operation efficiency, we would like to seek your co-operation to adhere to the following guidelines.

### Storage

<!--If your total namespace/group storage exceeds the available storage quota, all projects under the namespace/group will be locked. A locked project will not be able to push to the repository, run pipelines and jobs, or build and push packages. Therefore, Agency is encouraged to perform regular maintenance by using the following guidelines:-->

- **Each User personal Namespace:** Each User may create up to 10 projects maximum in GitLab in their personal namespace.
- **Each GitLab Group (SHIP-HATS Subscription):** Storage usage in the group should be within the size (i.e., 10 GB x Number of Users in the group).

Therefore, Agencies must perform regular [maintenance](#maintenance).

<!--- **Each repo:** Each repo size should be limited to 2 GB maximum.-->

<!--Agencies with specific requirements, please submit a service request or write to [enquiries_SHIP@tech.gov.sg](enquiries_SHIP@tech.gov.sg) for evaluation by the SHIP-HATS team. Requests will be reviewed based on actual use-case.-->

### Maintenance


A periodical review and maintenance are encouraged to ensure that the Group's storage is kept within the allocated size.

You may back up and store the following components in your own S3 bucket/storage services as required:
- Repository
- Artifacts
- Container Registry
- Package Registry
- Pipeline Results

?> **Note:** GitLab maintenance window is between Wednesday 9:00 PM SGT to Thursday 1:00 AM SGT 


### Shared Runners

- Shared runners should **not** be used to perform load testing. Agencies that need to conduct performance or load testing, please run the load test using your own dedicated runner.
- Shared runners will have a **default timeout if idling for more than 10 minutes**. This is to avoid impacting the availability of the shared resources.


### Jobs
- Schedule jobs only when necessary and during low peak hours (1.00 am - 8.00 am).
