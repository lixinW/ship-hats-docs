# Support

<!--**Topics**
- [Raise a service request](#raise-a-service-request)
- [Maintenance schedule](#maintenance-schedule)
- [FAQs](#faqs)
-->


## Raise a service request

- [Create a Service Request](https://jira.ship.gov.sg/servicedesk/customer/portal/11)

## Maintenance schedule


| Tool | Frequency/Timing | Impact to activity during this timing |
| --- | --- | --- |
| RDS: </br>Bitbucket</br>Bamboo</br>Jira</br>Confluence</br>Crowd </br>Gitlab | Daily, 2am to 3am |Database commits may fail. |
| NFS Snapshots: </br>Bitbucket </br>JIRA </br>Confluence </br>Crowd | Daily, 3am to 4am |New activity happening after the snapshot is initiated may not be included in snapshot. |
| EBS Snapshots:</br> Nexus Repo </br>Nexus IQ </br>Bamboo </br>LDAP </br>Gitlab | Daily, 3am to 4am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| NFS Backup to EBS | Daily, 4am to 5am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| S3 Bucket Snapshots: </br> Nexus Repo | Daily, 3am to 6am | Nexus Repo will be frozen while this is ongoing. (Read-only) |

## FAQs

>**Tip:** Click the triangle to view the answer.

<details>
  <summary><b> What is basic support?</b></summary><br>
Basic support is the support provided by SHIP-HATS team as per on the service agreement.
</details>
<br>
<details>
  <summary><b> How do I submit my requests for any support required? </b></summary><br>

Send an email to enquiries_enp@ship.gov.sg or submit a ticket on the [SHIP service desk (SSD) portal](https://jira.ship.gov.sg/servicedesk/customer/portal/11)</a>.

</details>
<br>
<details>
  <summary><b>What are the operating hours for basic support? </b></summary><br>
SHIP-HATS basic support to all users is offered from Monday to Friday, 9.00 AM to 5.30 PM.
Agencies can subscribe to the extended support hours as an add-on if required.
</details>
<br>
<details>
  <summary><b>What are the operating hours for extended support? </b></summary><br>
SHIP-HATS extended support is offered from Monday to Friday, 9.00 AM to 10.00 PM.
</details>
<br>
<details>
  <summary><b>Is the basic support free? </b></summary><br>
Yes, it is free with any subscription tier.
</details>
<br>
<details>
  <summary><b>What are the rates for extended support? </b></summary><br>
Extended support is charged at 50% of the total subscription based on the standard price.
  </details>
<br>
<details>
  <summary><b>Can I subscribe to Extended Support for a limited time? </b></summary><br>
Yes. A one-month advance notice is required. There is no pro-rated price and is computed as a full-month's rate. Hence, to maximise it is recommended to start on the 1st of any month.
</details>
<br>
<details>
  <summary><b>How do I subscribe to extended support? </b></summary><br>
Email enquiries_enp@tech.gov.sg to subscribe to extended support.
</details>
<br>
<details>
  <summary><b>How do I cancel extended support? </b></summary><br>
Email enquiries_enp@tech.gov.sg to cancel extended support.
</details>
<br>
<details>
  <summary><b>Can I view the history of my support requests? </b></summary><br>
Users can refer to their requests on the <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11">SSD portal</a>.
</details>
