# Compliance framework

In SHIP-HATS 2.0., we are leveraging Gitlab [Compliance Framework](https://docs.gitlab.com/ee/administration/compliance.html) feature. 

Using this feature, you can automate some DevSecOps practices that we encourage all agencies to adopt based on industry pipeline security as well as IM8 DevSecOps standards. The following list provides few of the DevSecOps practices supported by the Compliance Framework:
    - SCA including Dependency scanning 
    - SAST/DAST/Container scanning
    - Gating before deployment to high stake environments
    - Reports generation as part of provenance
    - Signing and verification of signature on artefacts 
    - Checksum verification of artefacts
    - Use of artifactory

<!--You have the option to not use the compliance framework but you are highly recommended to do so in order to reap the benefits of practising DevSecOps.-->

We will continuously review and improve the compliance framework to help meet more standards. We recommend that you apply [compliance pipeline](https://sgts.gitlab-dedicated.com/WOG/ship-hats-compliance) when building your pipeline.
