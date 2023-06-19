
Supply Chain Levels for Software Artifacts (SLSA) is an add-on component to SHIP-HATS that protects against supply chain attacks. The SLSA framework helps us  strengthen our defense against supply chain attacks.

## Why is SLSA required?

For an application, the software supply chain can grow to be very complex, comprising of code written by team engineers, external libraries and frameworks. A lot of different processes including testing, security scans, and building of software artifacts add to this complexity further. 

As the supply chain grows and become more complex, it becomes prone to software supply chain attacks. Increase in such attacks (e.g., SolarWinds, Codecov) over last few years makes it important that we implement and apply SLSA to our applications to ensure  integrity and security. 

## SLSA Levels

We aim to achieve [SLSA Security Level 2](https://slsa.dev/spec/v1.0/levels) for projects inside SHIP-HATS.

|Level|Description|
|---|---|
|SLSA Build Level 0| Project is not on SHIP-HATS GitLab and doesn't implement the SLSA framework requirements.
SLSA Build Level 1| Project is using SHIP-HATS GitLab CI/CD and generating attestation for their software artifact.
SLSA Build Level 2| Project is using SHIP-HATS GitLab CI/CD and generating attestation for their software artifact, and also signing and verifying their software together with the attestation.

?> [Read more on Build Levels](https://slsa.dev/spec/v1.0/levels)

## Achieving SLSA Build Level 2

To achieve SLSA Build Level 2, SHIP-HATS offers the following:

-   A template to  [generate GitLab attestation](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-slsa-commonyml)  for your software artifact
-   [Container template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-container-signingyml) and Blob [signing/verification template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-blob-signingyml)  to sign and verify your software and the supporting attestations.

## Applying SLSA to your project 

Applying SLSA to your project is **optional but recommended**.

1. **Generate** GitLab attestation for your software artifacts.
    -   Get the latest `v1.0.8` version of the  [generate attestation template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-slsa-commonyml).
    -   Include the `.generate-gitlab-attestation` template in the same job where you build your software artifact
    
    The job will now generate the attestation and save it as a job artifact.
1. **Sign** your software artifacts together with the generated attestation:

    -   Get the latest `v1.0.8` version of the  [container signing template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-container-signingyml)  or  [blob signing template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-blob-signingyml)
    -   Sign your software artifacts. If you do not have a job to sign the artifacts, you can create one and configure it to sign your software artifacts.
    -   In your signing job, include the  `ATTESTATION_FILE`  variable. This will tell the job to sign the attestation and link it to your signed software artifacts.
    -   In your signing job, you can optionally include the  `SIGN_ATTESTATION_OPTS`  variable (only for container signing, not for blob signing) if you want to customise the arguments when signing the attestation.
1. **Verify** your signed software artifacts together with the signed attestation before deployment:

    -   Get the latest `v1.0.8` version of the  [container verifying template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-container-signingyml) or [blob verifying template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-blob-signingyml)
    -   Verify the artifact. If you do not have a job to verify the artifacts, you can create one and configure it to verify your software artifacts.
    -   In your verifying job, include the  `ATTESTATION_PREDICATE_TYPE`  variable. For blob verification, the  `SIGNED_ATTESTATION_FILE`  variable is also needed. This will tell the job to verify the attestation for the software artifacts
    -   In your verifying job, you can optionally include the  `VERIFY_ATTESTATION_OPTS`  variable to customise the arguments when verifying the attestation.
    -   You can optionally create a  [Cue or Rego policy](https://docs.sigstore.dev/cosign/attestation#validate-in-toto-attestations)  that you can use to verify the contents of your attestation. When verifying the attestation, you can include the argument  `--policy <policy_file>`  in the  `VERIFY_ATTESTATION_OPTS`  to ensure that the contents of the attestation are checked against the policy.

## Software Bill of Materials (SBOMs)

A Software Bill of Materials (SBOM) is an inventory of software components that your software is comprised of. SBOMs are not part of SLSA, but complement SLSA to strengthen supply chain security. SBOMs can also be signed and verified together with your software artifact as an attestation.

## Generating SBOMs for your project 

Generating SBOMs for your project is **optional but recommended**.

### GitLab Dependency Scanning 

If you use GitLab Dependency Scanning, it will automatically generate a CycloneDX SBOM for you. Refer to [GitLab documentation](https://docs.gitlab.com/ee/user/application_security/dependency_scanning/#cyclonedx-software-bill-of-materials) for more details.

### GitLab Container Scanning 

If you use GitLab Container Scanning, it will automatically generate a CycloneDX SBOM for you. Refer to [GitLab documentation](https://docs.gitlab.com/ee/user/application_security/container_scanning/#cyclonedx-software-bill-of-materials) for more details.

### Nexus IQ 

To generate a Nexus IQ CycloneDX SBOM, you can use the SHIP-HATS template as follows:

-   Get the latest version `v1.0.8` of the  [Nexus IQ scan template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-nexus-iq-scanyml)
-   In your Nexus IQ scan job, include the  `NEXUS_IQ_SBOM_FILE`  variable. This will tell the job to generate the SBOM and save it as a job artifact.

### Aquasec Trivy

To generate a Aquasec Trivy CycloneDX SBOM, you can use the SHIP-HATS template as follows:

-   Get the latest version `v1.0.8` of the  [Aquasec Trivy scan template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-aquasec-trivy-scanyml)
-   In your Nexus IQ scan job, include the  `TRIVY_SBOM_FILE`  variable. This will tell the job to generate the SBOM and save it as a job artifact.

## Signing and Verifying SBOMs

Signing and verifying SBOMs in your project is **optional but recommended**.

After the SBOM files have been generated, you can sign and verify as a software attestation.

1. Sign your software artifacts together with the generated SBOM:

    -   Get the latest v1.0.8 version of the  [container signing template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-container-signingyml)  or  [blob signing template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-blob-signingyml)
    -   We assume you have a job to sign your software artifacts. If you do not have a job to sign the artifacts, you can create one and configure it to sign your software artifact.
    -   In your signing job, include the  `SBOM_FILE`  variable and  `SBOM_PREDICATE_TYPE`  variable. This will tell the job to sign the SBOM and link it to your signed software artifact.
    -   In your signing job, you can optionally include the  `SIGN_SBOM_OPTS`  variable (only for container signing, not for blob signing) to customise the arguments when signing the SBOM.

1. Verify your signed software artifacts together with the signed SBOM before deployment. This is an optional step and will be useful in the future. 

    -   Get the latest v1.0.8 version of the  [container verifying template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-container-signingyml) or [blob verifying template](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-blob-signingyml)
    -   We assume you have a job to verify your software artifacts before deployment. If you do not have a job to verify the artifacts, you can create one and configure it to verify your software artifact.
    -   In your verifying job, include the  `SBOM_PREDICATE_TYPE`  variable. For blob verification, the  `SIGNED_SBOM_FILE`  variable is also needed. This will tell the job to verify the SBOM for the software artifact
    -   In your verifying job, you can optionally include the  `VERIFY_SBOM_OPTS`  variable to customise the arguments when verifying the SBOM.


## SLSA and Compliance Framework

SLSA, SBOM, and Attestation mechanisms have been integrated with the [Compliance Framework v1.0.3](https://sgts.gitlab-dedicated.com/wog/ship-hats-compliance) and applied to [E2E templates](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates).

With the Compliance Framework v1.0.3 and E2E templates, the SBOM signing and verification will be automatically included in your pipeline. However, if you are using only Compliance template, you must complete the following steps:
1. Generate the attestation in your build job 
1. Pass the following variables:
    - `ATTESTATION_PREDICATE_TYPE`
    <!--: This variable is required if you want to verify the gitlab attestation. The gitlab attestation follows the "slsaprovenance" predicate type.-->
    - `VERIFY_ATTESTATION_OPTS` 
    <!--: This variable is for including extra arguments when verifying the attestation. "--check-claims=false" is required for gitlab attestation.  -->
    - `SIGNED_ATTESTATION_FILE` 
 
After the above conditions are met, the attestation signing and verification will be automatically included in your pipeline. **[[Read more here](https://sgts.gitlab-dedicated.com/wog/ship-hats-compliance)]**


### E2E Templates 

Attestation have been applied to the following templates: 

- SHIP-HATS Docker Image CI Pipeline Templates (v1.0.2)
- SHIP-HATS Docker Multi Services App E2E Templates (v1.0.2)
- SHIP-HATS Docker Single Service App E2E Templates (v1.0.2)
- SHIP-HATS Webapp E2E Templates (v1.0.1)

### Examples: E2E Examples

- [Docker Image CI App](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates/examples/docker-image-ci-app)  
- [Docker Multi Service App](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates/examples/docker-multi-services-app)
- [Docker Single Service App](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates/examples/docker-single-service-app)
- [Nodets Webapp](https://sgts.gitlab-dedicated.com/wog/gvt/ship/e2e-templates/examples/nodets-webapp) 

### Examples: SHIP-HATS Templates

- [Blob-Signing](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/blob/main/gitlab-ci/Blob-Signing.yml) | [Documentation](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/gitlab-ci#example-blob-signing) 

- [Container-Signing Example](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/blob/main/gitlab-ci/Container-Signing.yml) | [Documentation](https://sgts.gitlab-dedicated.com/wog/gvt/ship/ship-hats-templates/-/tree/main/gitlab-ci#example-container-signing)

## Additional Resources

-   SLSA Website:  [https://slsa.dev/](https://slsa.dev/)
-   SLSA Levels:  [https://slsa.dev/spec/v1.0/requirements#build-levels](https://slsa.dev/spec/v1.0/requirements#build-levels)
-   CycloneDx SBOM:  [https://cyclonedx.org/](https://cyclonedx.org/)
-   Sigstore:  [https://docs.sigstore.dev/](https://docs.sigstore.dev/)
-   Cosign:  [https://docs.sigstore.dev/cosign/overview](https://docs.sigstore.dev/cosign/overview)






<!--## Applying SBOM for SLSA

?> This is an optional feature. However, we recommend that you use this feature. **After you apply SBOM, you will be able to achieve SLSA Security levels 2.** 
-->
