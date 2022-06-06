# User Roles and Permissions

[SHIP-HATS](https://www.developer.tech.gov.sg/singapore-government-tech-stack/toolchain/overview.html) tenants are managed through subscriptions. Following roles and permissions are available to agencies and vendors within the SHIP-HATS web portal:

| **Role** | **Description** | **Permissions** |  
| --- | --- | --- |
| **Subscription Administrator (SA)** | Each subscription is managed by SA. Only an agency user can be assigned as an SA and there can be up to two SAs per subscription. By default, an SA has all the rights in a subscription. SAs can view the limit of projects, project admins, and users quota within the SHIP-HATS Portal pages. | Refer to [SA Permissions](#sa-permissions) for detailed permissions. |
| **Project Administrator (PA)** | A subscription can have multiple projects and each project is managed by PAs. An Agency user or a vendor can be assigned as a PA. <br> **Note:** The number of PAs that can be added to a project through the SHIP-HATS portal vary based on your subscription tier level. PAs can view the limit of projects, project admins, and users quota within the SHIP-HATS Portal pages. | Refer to [PA Permissions](#pa-permissions) for detailed permissions. |  
| **User** | User is the default role for all the users from the Agency and vendors. | Refer to [User Permissions](#user-permissions) for detailed permissions. For tool-specific permissions, refer to [Tools Permissions](#tools-permissions).|  

## SA Permissions
- Manage a subscription including upgrading or downgrading to a different tier from [SHIP-HATS Portal](https://www.ship.gov.sg/). For more information, refer to the [Subscription FAQs](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started-guide/#/subscription).
- Add users to a subscription and manage their roles.
- Create and manage projects. While creating a project, it is mandatory to assign at least one Project Administrator (PA). The maximum number of PAs allowed depends on your subcription model.
- Request or remove additional resources for a subscription. For more information refer to the [SHIP-HATS Portal](https://www.ship.gov.sg/). For more information, refer to the [Subscription FAQs](https://docs.developer.tech.gov.sg/docs/ship-hats-getting-started-guide/#/subscription).

## PA Permissions
- Manage project from [SHIP-HATS Portal](https://www.ship.gov.sg/).
- Add users to a subscription and manage their roles. Note that only SA can assign PA role to a user.
- Add tools to project.
- Add users to a project and manage their roles within the tools.

## User Permissions
- Perform assigned functional roles and responsibilities within the associated tool(s).

## Tools Permissions  

For user roles and permissions related to tools, refer to the Users and Permissions section in the [SHIP-HATS Tools guide](https://docs.developer.tech.gov.sg/docs/ship-hats-tools-guide/#/tools-overview). 
<!--
- [Bitbucket User Roles and Permission](bitbucket-user-role)
- [Bamboo User Roles and Permission](bamboo-user-roles)
- [Confluence User Roles and Permission](confluence-user-role)
- [Jira User Roles and Permission](jira-user-role)
- [Fortify User Roles and Permissions](fortify-user-roles-and-permissions)
-->