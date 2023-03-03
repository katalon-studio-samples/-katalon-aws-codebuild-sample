# Integrating Katalon Test Automation with Your AWS CodePipeline CI/CD Process

Katalon and AWS CodePipeline play a critical role in the continuous delivery process, where AWS CodePipeline automates the building and deployment of applications, and Katalon ensures the quality of the applications by automating end-to-end testing. By integrating Katalon into your AWS CodePipeline CI/CD Build process, you can ensure that you have comprehensive end-to-end test coverage in a fully automated way.  The integration between these two solutions will help you automate the build, test, and deployment of your applications.

To integrate these two applications, first we will store all Katalon automation test scripts in a code repository such as AWS CodeCommit or GitHub or any other Git-based SCM tool. We will then create a CodePipeline project and provide access to the code repository. Using a .yml file, we will then access Katalon automation test suites/cases and schedule them to be executed within your CI/CD build.  Finally, the results of test execution will be presented in the Katalon TestOps solution.

If you are currently using AWS CodePipeline and would like to automate your CD pipeline, or if you are an existing Katalon user planning to adopt AWS CodePipeline for build/release automation, the blog will provide all the details you will need to make the integration work.

# Requirements

* Create a project within katalon studio and Record Test and Commit Source Code into source code management(CodeCommit/Github etc).
* buildspec.yml: The buildspec file is YAML-formatted and is used to store build commands. You can get this file from our github repository with our sample project: Katalon Studio Samples.

* Valid Katalon API key: You can generate API keys via:
* Katalon TestOps
* Command generator in Katalon Studio.
* Refer to Generate API keys for more information about API key generation.
* Secret Manager: The Secret Manager protects the Katalon API key. To learn more about creating secret keys, refer to the following AWS documentation:
* Environment Variable AWS codebuild.
* Define environment variables.
* Katalon license: You must have a valid license to run Katalon tests. For more information on licenses, refer to Katalon license types.
You must be able to integrate your codebuild with Katalon TestOps to generate reports. You must also be connected to a repository (for example GitHub) so that you can push your codebuild project. Refer to TestOps Integration for more details.

# Create an AWS codebuild

* To create an AWS codebuild, perform the following steps:
* Sign in to Amazon Web Services, search for AWS CodeBuild, and go to the CodeBuild service.

The CodeBuild page appears.

![image](https://user-images.githubusercontent.com/84115288/222785934-28b3d57f-2f8f-4c39-b896-448e16547310.png)


# Click Create build project.
Details of the project appear. Fill in the following information:
Project information

Source

![image](https://user-images.githubusercontent.com/84115288/222785805-b2787b3c-7e75-4f9d-b987-7d03420ffb11.png)


Environment: When filling the fields in the Environment section, ensure that you select the Privileged checkbox if you wish to build Docker images or provide your builds with elevated privileges.

![image](https://user-images.githubusercontent.com/84115288/222786174-0975a929-15e9-4bda-a27b-7387c3bf9f5a.png)

Environment (Additional information): The Timeout and Queued timeout fields are pre-populated and you can change them as per your requirement.

Buildspec

![image](https://user-images.githubusercontent.com/84115288/222786391-06688c02-970c-47f9-a6cb-567e0d30ecfd.png)


# Click Create Build Project.
A project created message displays then you are good to Start build. Click on Start build.

![image](https://user-images.githubusercontent.com/84115288/222786553-e9d73c10-927e-4790-8005-fa02b49004d6.png)


# Click Build logs to monitor the build progress.

![image](https://user-images.githubusercontent.com/84115288/222786865-e6244640-9f48-438d-9785-60b0ac4563c4.png)

Once the codebuild is complete, you can view its report in Katalon TestOps. Refer to: View results in TestOps.

![image](https://user-images.githubusercontent.com/84115288/222787044-793d7eb9-d24b-4d86-80a3-c5e072b1c147.png)


![image](https://user-images.githubusercontent.com/84115288/222786749-bc01b25d-e9cb-4208-88cb-a36d786bae76.png)


