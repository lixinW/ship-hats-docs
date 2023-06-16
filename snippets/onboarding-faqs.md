
<details>
  <summary> Will the default GitLab project’s parent group name that is created for our agency always be the SHIP-HATS subscription name?	
 </summary><br>

Yes, the default GitLab project’s parent group name that is created for agency will always be the same as SHIP-HATS subscription name. If you want to rename the parent group, you must first rename the SHIP-HATS subscription title.

If you want to change the subscription title and parent group name, [raise a service request](https://docs.developer.tech.gov.sg/docs/ship-hats-support/raise-service-request). In the **Summary** field of the ticket, indicate `SHIP-HATS 2.0 GitLab - <your request>`

For more information on the groups, refer to our [GitLab Groups](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/architecture?id=gitlab-groups) documentation. 

</details>



<details>
  <summary>Since the subscription model includes GitLab Native tools, do we still need to subscribe to other tools such as SonarQube? Is there a checklist on the difference between the tools that we can refer to? </summary><br>

Choice of tools depends on agency-specific use case and requirements. Refer to our [Tooling Strategy and Assessment](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started/ship-hats-tools?id=tooling-strategy)
</details>



<details>
  <summary>Can my Confi system be onboarded to SHIP-HATS 2.0 ? </summary><br>

Do note that:

- SHIP-HATS does not store your production transactional data.
- SHIP-HATS only store your source codes, configurations files.
- SHIP-HATS will only run a transient instance of your application (without production data and only assessable within ship-hats)
for security scanning and automated functional testing activities.

A possible way ahead for your Confi systems to be on SHIP-HATS 2.0:

1. Classify your source codes as Confi(cloud) or below
    - This will not change your total system classification as it will remain as Confi
    - There is no need to re-classify any other system components (e.g., transactional Data)
1. With only your source code classified as Confi(cloud) you could leverage on SHIP-HATS for your CI/CD requirements.

</details>



