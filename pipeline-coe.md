# Pipeline COE

**[Pipeline COE](https://sgts.gitlab-dedicated.com/innersource/projects/sgts-pipelinecoe)** is a Gitlab project that aims to build and store images that all logged in users on SHIP-HATS Gitlab Dedicated can use.

Pipeline COE is an internal project (not a private project) where all logged in users are able to view, raise MRs, and run pipelines on non-protected branches.

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

1. Add on to a current project by [raising a service request]() for us to elevate their role to "Developer" to raise a MR for its Dockerfile changes to add/change the image. Platform team will assess and merge accordingly subjected to approval.
1. If the requirements do not fit into any of the existing projects, [raise a service request]() for us to create a project within Pipeline COE and raise an MR there for us to do #1.
1. [Raise a service request]() for platform team to help.

## Approval Tips

- Pass scans
- No deprecated versions. As we would like to keep the images within Pipeline COE as clean as possible, we will deprecate versions with proper communication to users. Should they still require the versions that we do not support, they may make a copy of the image in their own container registries.
- Reusability (Highly customised images or images that contains users' specific development work are better to be stored in users' own container registries)

## Future Enhancements

- Automation for announcements when an image is about to be deprecated
- Maintenance rules
- Add all users as developers as member to Pipeline COE