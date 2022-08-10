This is a hands-on tutorial that provides an introduction to the use of templates and compliance developed by SHIP-HATS.

**Topics**
- [How to use this tutorial](#how-to-use-this-tutorial)
- [Prerequisites](#prerequisites)
- [Fork this tutorial](#fork-this-tutorial)
- [Checkpoint 1 - Configure E2E template](#checkpoint-1---configure-e2e-template)
- [Checkpoint 2 - Configure build](#checkpoint-2---configure-build)
- [Checkpoint 3 - Configure test](#checkpoint-3---configure-test)
- [Checkpoint 4 - Configure deployment](#checkpoint-4---configure-deployment)
- [Checkpoint 5 - Configure runtime test](#checkpoint-5---configure-runtime-test)
- [Checkpoint 6 - Configure publish To Nexus](#checkpoint-6---configure-publish-to-nexus)
- [Checkpoint 7 - Apply compliance framework](#checkpoint-7---apply-compliance-framework)
- [Checkpoint 8 - Apply compliance framework to use different toolchain (FOD SAST, FOD DAST)](#checkpoint-8---apply-compliance-framework-to-use-different-toolchain-fod-sast-fod-dast)
- [Achievements through tutorial](#achievements-through-tutorial)
- [Links and documentation](#links-and-documentation)
- [Call for contribution / innersourcing](#call-for-contribution--innersourcing)



# How to use this tutorial

The tutorial comprises of a list of checkpoints to guide users to build and deploy a simple Python web application while adhering to the DevSecOps practices and being as compliant as possible.

In each checkpoint, users will complete some step-by-step development work that will help the users learn to use the templates and their design rationale.  

Branches numbered in sequence have been provided in this repository. These branches contain the code that should be `<used/included?>` at each checkpoint.  

Users can also use them to skip ahead by merging the relevant checkpoint to their branches. For example, for skipping to checkpoint 4, users can run `git merge` for checkpoint 4.

# Prerequisites

* TP User account 
* BYO SEED/DEEP-enabled device
* Deployment target
* Nexus Repo test account
* Nexus IQ test account
* FOD DAST/SAST test account

# Fork this tutorial

Let us begin with an example Python web app that you need to build and deploy. Complete the following steps:

1. Fork this tutorial by accessing [this URL](https://gts.gitlab-dedicated.systems/compliance/govtech/workshop/tutorial/web-app-tutorial) 
    1. In the top-right of the page, select **Fork**
    1. Enter values in the available fields. Make sure that **Project URL** is set to *compliance/govtech/Workshop/Exercise*. 

        >**Note:** The requirement to sign commits using GPG signature is disabled only for the purpose of this workshop. In your live development, make sure to follow the global setting and set up your machines to sign commits as a best practice. For more information, refer to https://docs.gitlab.com/ee/user/project/repository/gpg_signed_commits/ 

2. Clone from your newly forked project and run using the following line of code:

    ```
    git checkout master

    ```

3. Validate and make sure that there is no file named **.gitlab-ci.yml**. This filename is reserved for the default pipeline definition in Gitlab. Running a pipeline to build and deploy the web app would require this file to be defined.


# Checkpoint 1 - Configure E2E template

To configure E2E template, you require a `.gitlab-ci.yml` file that you can build from scratch or you can try to find a match in use-case defined within the [SHIP-HATS E2E Templates](https://gts.gitlab-dedicated.systems/compliance/e2e-templates). For our example, we will use the relevant webapp E2E template provided in the [SHIP-HATS E2E](https://gts.gitlab-dedicated.systems/compliance/e2e-templates/webapp-e2e) templates. The instructions for usage are provided in its `README`.

To put the Python webapp source codebase alongside the E2E template, you can use one of the following options:

* Create a repository clone from the E2E template, and then copy the Python webapp files in the newly cloned repository.
* Clone E2E template repo locally, and then push its files to the Python webapp repository.
* Fork from E2E template repo.
* Create a `.gitlab-ci.yml` file and include the E2E template's `.gitlab-ci.yml` by adding the following lines of code:

  ```
  include:
    - project: "compliance/e2e-templates/webapp-e2e"
      ref: "main"
      file:
        - .gitlab-ci.yml
    - local: BUILD.gitlab-ci.yml
    - local: TEST.gitlab-ci.yml
    - local: DEPLOY.gitlab-ci.yml

  ```

>**Note:** Each of the above options has its own pros and cons. 
> - The copy/fork method would require more manual maintenance  
> - The inclusion method would mean that if the E2E template pipeline changes, your pipeline could be affected without prior knowledge or notice.  
>There is ongoing development of release management plans of the templates and compliance.

1. Run the following lines of code:

    ``` 
    git checkout master

    git merge origin/checkpoint-1/configure-e2e-template
    ```

3. Observe that: 
    * The E2E template files has been placed alongside with the Python webapp by whichever method specified, except for the inclusion method.
    * `.gitlab-ci.yml` has standard stages defined to build and deploy a web application. The stages are important for compliance to be applied later on. **Do not rename or change them. You can, however, customise the definition of the jobs within as and when needed.** 
    * Any customisation, such as app-specific or language-dependent steps, are to be placed inside of the files `BUILD/TEST/DEPLOY.gitlab-ci.yml` as the E2E templates are designed to be language-agnostic. You will also be required for fill up the variables section (All of the required details are covered either in E2E templates documentation or later on in this tutorial).
    * Observe the usage of modular templates in `.gitlab-ci.yml`. The wait for service to be up first before integration testing is leveraging [wait-for-app-and-assert-text](https://gts.gitlab-dedicated.systems/templates/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-check-app-readinessyml) from SHIP-HATS templates. The use of it takes away the complexity of bash development. You may find other templates useful as they are built to be modular and reusable with great care also given to security aspects.

# Checkpoint 2 - Configure build

We need to define the app-specific details such as how to build the webapp, which can be done in BUILD.gitlab-ci.yml file. 

1. Run: 
    ``` 
    git checkout master

    git merge origin/checkpoint-2/configure-build
    ```

2. Observe BUILD.gitlab-ci.yml. `build-job` has been defined to build this Python webapp. If you are building a Ruby or Java application, the customised scripts can go in here. You may find some examples [here](https://gts.gitlab-dedicated.systems/compliance/e2e-templates/e2e-examples). 

3. Observe .gitlab-ci.yml. `WORKING_DIR=pythonapp` and `OUTPUT_ARTEFACT=$WORKING_DIR/pythonapp.zip` has been defined. WORKING_DIR is referenced by BUILD.gitlab-ci.yml as it will run the build command in the directory to produce an OUTPUT_ARTEFACT. OUTPUT_ARTEFACT should be the path to the file of the binary or zipped folder that is to be eventually deployed. It is also used by compliance later for scanning and signing as well as for verification of checksum.

# Checkpoint 3 - Configure test

We need to define the app-specific way of testing the webapp, which can be done in TEST.gitlab-ci.yml file. Unit/integration testing, language-based linting, framework-based dependency checks and E2E testing should be included here.

1. Run: 
    ``` 
    git checkout master

    git merge origin/checkpoint-3/configure-test
    ```
2. Observe TEST.gitlab-ci.yml. It includes some very framework/app specific ways of checking for dependencies, linting, and unit/integration testing using "pip check", "pylint", "pytest".

3. Modify the following variables in .gitlab-ci.yml and personalise it to your liking:

    |Variable|Description|
    |--------|-----------|
    |NAME|Name to be displayed in the webapp and for tests, spaces to be separated/delimited by an additional backslash eg. If your name is John Smith, NAME='John\ Smith'|
    |COLOR|Color of header in the webapp (CSS color scheme)|

4. Push changes to master branch:
    ```
    git checkout master
    git add .gitlab-ci.yml
    git commit -m "Personalised variables added in .gitlab-ci.yml"
    git push origin master # trigger pipeline to run
    ```

5. Observe the pipeline status. This can be done through the **Pipeline** section under **CI/CD** in the navigation bar. Click on the pipeline under the status column accordingly. The various jobs and stages defined in .gitlab-ci.yml can now be seen. To view the output of each job, click on the individual job.

6. Verify that the pipeline passes the `static-test` stage but fails at the `deploy-to-testing-env` stage

# Checkpoint 4 - Configure deployment

We need to define the infrastructure-specific way of deploying the webapp, which is heavily dependent on how the application is to be hosted. Its definition should be included inside DEPLOY.gitlab-ci.yml file. 

1. Run: 
    ``` 
    git checkout master

    git merge origin/checkpoint-4/configure-deploy
    ```

2. Observe .gitlab-ci.yml. `WEBAPP_NAME="Python Webapp"` has been defined. This is the value used by `wait-for-web-app-ready-job` to check whether the webapp is up. `WEBAPP_URL="ec2-18-139-176-29.ap-southeast-1.compute.amazonaws.com:$PORT"` has also been defined. This is the URL used by `wait-for-web-app-ready-job` to check whether the webapp is up so that `e2e-test-job` can run integration tests.

3. Define `PORT=<user_port>` in .gitlab-ci.yml. For classroom-conducted trainings, please check with the trainer for your specific port number.

4. Define `UNZIPPED_DIR=<user_app_dir>` in DEPLOY.gitlab-ci.yml. **<user_app_dir>** should not have any whitespaces. For classroom-conducted trainings, please check with the trainer for your specific directory name.

5. Push changes to master branch:
    ```
    git checkout master
    git add DEPLOY.gitlab-ci.yml .gitlab-ci.yml
    git commit -m "User definition in deploy stage."
    git push origin master # trigger pipeline to run
    ```

6. Observe DEPLOY.gitlab-ci.yml. The steps are used for deployment to staging environment for running E2E tests against and also later on reused for final deployment to production environment. This consistency is important to omit any possibilities of the webapp being deployed wrongly. 

7. Observe the usage of modular templates. In DEPLOY.gitlab-ci.yml, fetching of the SSH key from AWS Secrets Manager is leveraging [**invoke-awssecretretrieval**](https://gts.gitlab-dedicated.systems/templates/ship-hats-templates/-/tree/main/templates#file-gitlab-ci-awsyml) from SHIP-HATS Templates. The use of it takes away the complexity of role assumption and more importantly, it uses a method that requires no storage of secrets like AWS_SECRET_ACCESS_KEY and AWS_ACCESS_KEY_ID. The templates are building blocks developed by the platform team to help users fix up pipelines quicker and safer and the project is open for innersourcing welcoming contributors from users. See [CONTRIBUTING.md](https://gts.gitlab-dedicated.systems/templates/ship-hats-templates/-/blob/main/CONTRIBUTING.md).

8. Verify that the pipeline fails due to missing variables in the `runtime-test` stage.

9. Observe "Deployments" > "Environments". A "testing" environment is up and running. `deploy-testing-job` with "environment:name" set to "testing" in DEPLOY.gitlab-ci.yml automatically enables this. You can select the "testing" environment then "View Deployment" to see the actual webapp through your browser and verify it is up.

# Checkpoint 5 - Configure runtime test

1. Run: 
    ``` 
    git checkout master

    git merge origin/checkpoint-5/configure-runtime-test
    ```
2. Observe the following variables in .gitlab-ci.yml which have been filled:

    |Variable|Value|Description|
    |--------|-----|-----------|
    |VERSION|1.0|Version of web app published to artefact repository|
    |RF_TESTSCRIPT_FOLDER|tests/e2e|Path to robotframework test script for runtime testing|
    |OPTS in `e2e-test-job`|-v BROWSER:headlesschrome -v URL:$WEBAPP_URL| Webapp URL added for runtime test|

3. Verify that the pipeline is now passing runtime-test stage.

4. A point to emphasise is that such tests may vary based on different frameworks/languages used in development. It is okay to override the job's implementation; the use of RobotFramework may not be for everyone, it is included in the E2E template as a starter/guide and a reminder for users the importance of having E2E tests for compliance.

# Checkpoint 6 - Configure publish To Nexus

1. Run: 
    ``` 
    git checkout master

    git merge origin/checkpoint-6/configure-publish
    ```
2. Observe the following variables in .gitlab-ci.yml which have been filled:

    |Variable|Value|Description|
    |--------|-----|-----------|
    |MAVEN_SETTINGS_SERVER_ID|ship-raw-test|Variable for `publish-maven-artefact` template|
    |MVN_SETTINGS_FILE|settings.xml|Variable for `publish-maven-artefact` template|
    |NEXUSREPO_REPO_ID|ship-raw-test|Variable for `publish-maven-artefact` template|
    |NEXUSREPO_REPO_GROUP_ID|workshop-python|Variable for `publish-maven-artefact` template|
    |ARTEFACT_PACKAGE|zip|Variable for `publish-maven-artefact` template|

3. Define `ARTEFACT_ID=<artefact_name>` in .gitlab-ci.yml. **<artefact_name>** should not have any whitespaces. This is the name of the artefact that will be pushed to the Nexus Repo. For classroom-conducted trainings, please check with the trainer for your specific artefact name.

4. Verify that the pipeline passes the publish stage and the pipeline runs successfully.

5. Push changes to master branch:
    ```
    git checkout master
    git add .gitlab-ci.yml
    git commit -m "ARTEFACT_ID customised."
    git push origin master # trigger pipeline to run
    ```

6. Verify that the pipeline passes runtime testing job and publish job.

7. As the `deploy-final-job` to deploy to production environment is configured to be triggered manually, in the navigation bar, select the job through "CI/CD" > "Pipelines" > select the most recent pipeline > trigger the `deploy-final-job` by clicking the "play" button.

8. Observe the pipeline jobs and dependencies. Using E2E template helps in:
    * Ensuring the required pieces of a CI/CD pipeline is present with the definition of sequence of events. 
    * Users' pipeline uses an artefactory in between build/test and deploy.
    * Segregation of responsibilities between build/test and deploy.

9. Finally, observe "Deployments" > "Environments" in the navigation bar again. A "production" environment is up and running and added on top of the previous "testing" environment. `deploy-final-job` with  "environment:name" set to "production" in DEPLOY.gitlab-ci.yml automatically enables this. You can select the "production" environment then "View Deployment" to see the actual webapp through your browser to verify it is up. You may have different environment values (staging) set for different branches. Possible names for environments: https://docs.gitlab.com/ee/ci/yaml/index.html#environmentdeployment_tier. You may protect your environment as per: https://docs.gitlab.com/ee/ci/environments/protected_environments.html.

# Checkpoint 7 - Apply compliance framework

Now that the pipeline is complete, the Python webapp pipeline is able to build and deploy the Python webapp as demonstrated. However, the pipeline is still lacking in terms of the Security component in DevSecOps. To fulfil compliance, we can apply the relative compliance framework and see the value that it adds.

1. Apply compliance by selecting "Settings" > "General" > "Compliance framework" > "ship-hats-webapp-compliance" in the navigation bar.

2. Set compliance-required variables by selecting "Settings" > "CICD" > "Variables".
   |Variable|Value|Description|
   |--------|-----|-----------|
   |COSIGN_PASSWORD|ship-raw-test|Variable for `publish-maven-artefact` template|
   |NEXUS_IQ_USERNAME|*CI/CD variable*|Variable for compliance framework Nexus IQ scan|
   |NEXUS_IQ_PASSWORD|*CI/CD variable*|Variable for compliance framework Nexus IQ scan|
   |NEXUS_IQ_APP_ID||Variable for compliance framework Nexus IQ scan|

3. Trigger pipeline by selecting in the navigation bar "CI/CD" > "Pipelines" > "Run pipeline" > Select "master" under "Run for branch name or tag" > "Run pipeline".

4. Run the pipeline and observe the additional compliance jobs. Using the webapp compliance framework helps in:
    * Ensuring the checksum/signature verification in between pushing the artefact to the repository and pulling it for deployment.
    * Static scans including secret detection scans are in place.
    * DAST is in place.
    * Reports are generated as part of provenance and visibility.

5. Upon completion of the run, observe "Security & Compliance" > "Security dashboard" in the navigation bar.

6. Observe "Security & Compliance" > "Vulnerability report" in the navigation bar.

7. Show the compliance framework and highlight that it cannot be overwritten.

# Checkpoint 8 - Apply compliance framework to use different toolchain (FOD SAST, FOD DAST)

1. Add toolchain credentials variables by selecting "Settings" > "CI/CD" > "Variables" > "Add variable" for all 3 FOD variables in the navigation bar.
   |Variable|Value|Description|
   |--------|-----|-----------|
   |FOD_USERNAME||Variable for compliance framework FOD scan|
   |FOD_PAT||Variable for compliance framework FOD scan|
   |FOD_RELEASE||Variable for compliance framework FOD scan|

2. Trigger pipeline by selecting in the navigation bar "CI/CD" > "Pipelines" > "Run pipeline" > Select "master" under "Run for branch name or tag" > "Run pipeline".

3. Observe that if credentials are provided, it will use the toolchain, which in this case is FOD. Otherwise, the compliance will fallback to use Gitlab native tools.


# Achievements through tutorial

* Ease of CI/CD development - templates, E2E templates
* Leverage on Gitlab's OTS security tools
* Leverage on Gitlab's reporting and scorecards
* Can be on future leaderboard scoring for QD. (Unconfirmed)
* Be more **compliant**, as per CNCF white paper 
  * Pipeline as code with commit history
  * Sign and verify artefacts
  * SAST and SCA
  * Prioritizing trusted package managers and repositories by the fetching of libraries and images via Nexus Repo 
  * Standardization of pipelines across projects 
  * Uploading of artefacts (even as images) to artifactory in this case, Nexus Repo

TODO:
- Amend compliance to be able to switch toolchain (https://gts.gitlab-dedicated.systems/compliance/ship-hats-compliance/-/issues/32
)

# Links and documentation
* [Modular templates](https://gts.gitlab-dedicated.systems/templates/ship-hats-templates)
* [End-to-end templates](https://gts.gitlab-dedicated.systems/compliance/e2e-templates) and [examples](https://gts.gitlab-dedicated.systems/compliance/e2e-templates/e2e-examples)


# Call for contribution / innersourcing
* [Modular templates](https://gts.gitlab-dedicated.systems/templates/ship-hats-templates)
* [End-to-end templates](https://gts.gitlab-dedicated.systems/compliance/e2e-templates) and [examples](https://gts.gitlab-dedicated.systems/compliance/e2e-templates/e2e-examples)
* Compliance
