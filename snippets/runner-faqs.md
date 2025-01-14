<!--

?>**Tip:** Click the triangle or question to view the answer.

-->



<details>
  <summary>Can we use Shared Runners for running large size docker images?	 </summary><br>

The Shared Runners will not be able to accommodate large size docker image. In this scenario, we recommend that you use own runners where you will have more control over the storage size of the runner itself.

Refer to [steps to set up your own runners](./gitlab-runners.md) and [Runners](./runners.md).
</details>



<details>
  <summary> What are the types of runners available on SHIP-HATS 2.0?</summary><br>


There are 3 types of runners available for our subscribers:

- SHIP-HATS Shared Runners are self-hosted runners in a scalable environment.
- GitLab Shared Runners are SaaS based shared runners. 
- Agency-hosted Remote Runners are dedicated runners set up in the agency environment. 

</details>



<details>
  <summary> Will the subscribers be able to host their our own GitLab runners?</summary><br>

Yes, the subscribers can host remote runners in their own environment. 

</details>



<details>
  <summary> What are the agents that we use for deployment? </summary><br>

Runners (Shared or Dedicated) are used for deployment in SHIP-HATS.

</details>




<details>
  <summary> Can the shared runner access our servers in GCC or OnPrem? </summary><br>

For GCC, the users can use SHIP-HATS Shared Runner and for OnPrem, users need an Agency-hosted Remote Runner. 

</details>



<details>
  <summary>Can SHIP-HATS integrate with other SaaS such as Salesforce? </summary><br>

Every SaaS has different integration capability. Therefore, it depends on the product.

</details>



<details>
  <summary> Can the GitLab Shared Runner download packages from the internet?</summary><br>

All the packages from the internet have to proxy through Nexus on SHIP-HATS for security reasons. 

</details>



<details>
  <summary>Can we have Mac OS runners in GitLab? </summary><br>

We do **not** have Mac OS runner support at the moment. For now, we suggest that you try hosting your own Mac OS runners.
</details>



<details>
  <summary>How powerful is the shared runners? For example, what’s the storage and RAM? </summary><br>

Default runner (CStack runner) has 40GB and 2vCPU and 8GB mem. Docker machine is t3.large. Agencies may [set up their own self-hosted runners](./gitlab-runners.md), if they require different settings.

</details>



<details>
  <summary>Are we offering Windows runners to run .NET framework/.NET Core? </summary><br>

Yes.

</details>



<details>
  <summary>Is there a maximum job timeout? </summary><br>

There is a project settings for runner timeout. The default timeout is set to 1 hour and maximum is 1 month as per the documentation. However, all these are subject to overall runner setting of 1 hour timeout regardless.
</details>



<details>
  <summary>How to run integration tests against my intranet service?</summary><br>

For intranet deployment, you need to use self host runner in intranet to do integration tests against your intranet service by providing the required network access.
</details>



<details>
  <summary>Can we use self-hosted runners? </summary><br>

It is safe to use the shared runners provided by SHIP-HATS team if agencies’ deployment environment is accessible by the runners (i.e. GCC AWS). Depending on your agency use cases, you can choose to [set up your self-hosted runners](./gitlab-runners.md). 
</details>



<details>
  <summary>What will be the cost for using runners? </summary><br>

There is no additional cost for using shared runners. There is charges for VPC connection endpoint (AWS cost) and the cost for hosting your own runners (i.e. EC2).
</details>



