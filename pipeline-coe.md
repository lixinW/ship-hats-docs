# Pipeline COE

**[Pipeline COE](https://sgts.gitlab-dedicated.com/innersource/projects/sgts-pipelinecoe)** is a Gitlab project that aims to **build and store images** that all logged in users on SHIP-HATS Gitlab Dedicated can use.

Pipeline COE is an internal project (not a private project) where all **logged in users are able to view, raise Merge Requests (MRs), and run pipelines on non-protected branches**.

### Audience

CI/CD Pipeline authors 

## Benefits of Pipeline COE

Using Pipeline COE, you can reduce redundancy by having a consolidated place where commonly used images by runners can be defined and stored. 

### Key Features & Takeaways

- Availability of Open source code that builds the images
- Integration of container scanning in build pipeline to ensure all images in CR are scanned
- Curated by deprecating versions with security vulnerabilities with regular clean ups and scans
- Up to date & patched base image

?> **Note:** For Bamboo users, this process is similar to the maintenance of custom images on top of SHIP's golden image, where golden image is the equivalent base image in Pipeline COE.

## Using Pipeline COE

When users are looking for an image to define for runners to use, they should look at the available ones in Pipeline COE. In the event that they are not able to find one, they may:

If you are looking for an image to define for runners to use, you can look for the same in the available resources in the Pipeline COE. If you are not able to find an image as per your requirement, you can:

1. [Raise a service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to update your role to **Developer** to add/change the image to the current project. SHIP-HATS team will then review and merge the request as per their approval process. 
1. If the requirement does not fit into any of the existing projects, [raise a service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to create a project within Pipeline COE. You can then raise a **Merge Request (MR)** for the SHIP-HATS team to complete step 1.
1. For any additional help, please [raise a service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to get support. 


## Approval Tips

- Make sure that **scans have passed** successfully.
- Make sure that there are **no deprecated versions**. To keep the images within Pipeline COE clean, we will deprecate versions with proper communication to users.  
    
    If there are versions that you require that are not supported or deprecated, you can make a copy of the image in your own container registries.

- Make sure that the **images are reusable**. If you have highly customised images or images that contains your specific development work, please store them in your own container registries.

## Future Enhancements

- Automation for announcements when an image is about to be deprecated
- Maintenance rules
- Add all users as developers as member to Pipeline COE