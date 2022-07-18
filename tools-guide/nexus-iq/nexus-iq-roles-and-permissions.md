# Roles and Permissions

User roles and their permissions determine the actions a user can perform in NexusIQ. NexusIQ as a COTS product comes with system defined roles and permissions. We have customised these system-defined roles and permissions to meet your requirements.

The following table lists the roles and permissions available on NexusIQ with SHIP-HATS.

|Roles |Permissions|
|---|---|
|Applicaton Evaluator|Evaluates applications<br>Views policy violation summary results|
Application Security Tester|Tests security vulnerabilities<br>Can change security vulnerabilities|
Component Evaluator|Evaluates inidvisual components<br>Views policy violation results for a specific application|
Developer|Views all information for their assigned organisation or application|
Legal Reviewer|Reviews legal obligations for component licenses|
---
<!--https://confluence.ship.gov.sg/display/SHIP/Nexus+IQ+Roles-->
IQ Server has several built-in roles, which are shown below. If one does not suit your needs, you can create a custom role.

Administrator Roles:

System Administrator - Manages system configuration and users, which includes LDAP and product license management as well as the ability to assign other users to the System Administrator role.
Policy Administrator - Provides full control over organizations, applications, policies, policy violations and custom roles.
Organizational Roles: 

Below is the list of roles and their privilages shown.

Owner-Manages assigned organizations, applications, policies, and policy violations and cannot claim components

<picture>

Owner with claim components - Manages assigned organizations, applications, policies, and policy violations and can claim components

<picture>

Developer - Views all information for their assigned organization or application.
<picture>

Application Evaluator - Minimum access to scan the application via the CI integrations. Evaluates applications and view policy violation summary results within the CI.


<picture>
Component Evaluator - Evaluates individual components and view policy violation results for a specified application within the IDE integrations.


<picture>

Project Admin- Can add application, view policy, violations but cannot claim components

<picture>

Application Security Tester v2  - 
Key responsibility: Review policy violations and edit vulnerability status/comment
Personnel: May be GT user or application vendor user if project team plans to have a vendor user or another GT user go through the findings first and update the analysis before the Security Lead reviews the analysis and suppresses false positives.  
Included in Onboarding form

<picture>