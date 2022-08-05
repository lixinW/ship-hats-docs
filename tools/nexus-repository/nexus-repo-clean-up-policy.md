# Cleanup policy

This section provides an overview on SHIP-HATS cleanup policy for your Nexus Repositories and recommendations that you can follow to improve performance and maintenance.

## Audience

SHIP-HATS users

## Why do we need a cleanup policy?

A cleanup policy helps to purge unnecessary components to optimise disk space supporting better performance. SHIP-HATS leverages upon [Sonatype's Cleanup feature](https://help.sonatype.com/repomanager3/repository-management/cleanup-policies) to manage components at repository level.

## SHIP-HATS cleanup policy

Our default cleanup policy is configured to automatically delete a component from your nexus repository after 180 days from the date of its creation. Our cleanup policy is at repository level and not at subscription/billing account level.

This policy is applied to your repositories from October 11 2021, and the task is scheduled to run daily at 01.00 AM.

We highly recommend you to periodically review your repositories and to maintain them from your end.

## FAQs

[Clean up FAQs](./snippets/clean-up-policy-faqs.md ':include')


### Related topics

- [Clean up docker repo](nexus-repository/nexus-repo-clean-up-docker-repo) 