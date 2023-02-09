**Libraries**

|Component|Path|
|---|---|
**JAVA_HOME**|  C:\Program Files\OpenJDK\openjdk-11.0.15_10
**Git**|  C:\Program Files\Git
**Visual Studio IDE**|
**MSBuild17_PATH**| C:\Program Files\Microsoft VisualStudio\2022\BuildTools\MSBuild\Current\Bin
**MSBuild16_PATH**| C:\Program Files (x86)\Microsoft VisualStudio\2019\BuildTools\MSBuild\Current\bin 
**MSBuild15_PATH**| C:\Program Files (x86)\Microsoft VisualStudio\2017\BuildTools\MSBuild\Current\bin 
**.NET SDK**|C:\Windows\Microsoft.NET\Framework64\v4.0.30319 - v4 (64 bit)<br><br>C:\Windows\Microsoft.NET\Framework\v4.0.30319 -v4(32 bit)
**AppDeployment Toolkit**|C:\PADT\Toolkit
**VS2017_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2017\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**VS2019_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2019\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**VS2022_TEST_PATH**|C:\Program Files (x86)\Microsoft VisualStudio\2017\TestAgent\Common7\IDE\CommonExtensions\Microsoft\TestWindow
**Microsoft VS Code**|C:\Program Files\Microsoft VS Code<br>Chocolatey v1.1.0<br>Scoop<br>nano 6.3-7<br>Vim

**Note the following when using Windows Runner:**

- Windows Runner has been set to run one job per instance at a time. 
- Windows Runner includes a cleanup job to remove all the downloaded and build artefacts after the job completes. For this cleanup job to work, you must use `git clone` (instead of `git fetch`) in your.NET project settings. If you use `git fetch`, the folder becomes unremovable.
    To change the project settings, you can follow one of the following methods:
    - Go to **Settings** > **CI/CD** > **General Pipelines** > **Git strategy**, and then select **Git clone**.

    ![Git Strategy Properties](./images/git-strategy-properties.png)

    OR  
    - Enforce `git clone` in your `gitlab-ci.yml` file by setting the `GIT_Strategy` variable to: `GIT_STRATEGY: clone`

    ![Git Strategy Command Line](./images/git-strategy-cmd.png ':size=40%')

-  Since the cleanup job has been enabled in Windows Runner to clean up everything after the job completes, you must push the artefacts to their repository (e.g. Nexus) to ensure data safety.
- You must complete the necessary cleanup after the build is completed by deleting any password or confidential files that might have been created or downloaded during the build job (e.g., docker config).