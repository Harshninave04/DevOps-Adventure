
![jenkins-image](./Assets/jenkins_hero.png)

# Jenkins for Beginners

Welcome to your DevOps journey! In this documentation, we'll explore the fundamentals of Jenkins, a powerful open-source automation server that can help streamline your software development and deployment processes.

## What is Jenkins?

Jenkins is a popular continuous integration (CI) and continuous deployment (CD) tool that automates the building, testing, and deployment of software applications. It provides a user-friendly web interface and a vast ecosystem of plugins that allow you to customize and extend its functionality to suit your specific needs.

## Key Features of Jenkins

1. **Continuous Integration**: Jenkins helps you automatically build, test, and integrate your code changes, ensuring that your application is always in a deployable state.

2. **Continuous Deployment**: With Jenkins, you can set up automated deployment pipelines that can push your application to various environments, such as development, staging, and production.

3. **Scalability and Flexibility**: Jenkins is highly scalable and can handle projects of any size, from small personal projects to large enterprise-level applications. It also supports a wide range of programming languages, tools, and platforms.

4. **Plugin Ecosystem**: Jenkins has a vast and active plugin ecosystem, allowing you to extend its functionality to meet your specific needs, such as integrating with version control systems, cloud platforms, and various testing frameworks.

5. **Distributed Builds**: Jenkins can distribute build and test tasks across multiple machines, improving the overall efficiency and speed of your build and deployment processes.

6. **Reporting and Monitoring**: Jenkins provides comprehensive reporting and monitoring capabilities, allowing you to track the status of your builds, tests, and deployments, as well as identify and address any issues that may arise.

## Getting Started with Jenkins

To get started with Jenkins, you'll need to follow these steps:

1. **Install Jenkins**: You can download and install Jenkins on your local machine or a dedicated server. Jenkins is available for various operating systems, including Windows, macOS, and Linux.

2. **Set up a Jenkins Project**: Once Jenkins is installed, you can create a new project (also known as a "job") to automate your software development and deployment processes.

3. **Configure the Project**: In your Jenkins project, you'll need to configure various settings, such as the source code repository, build triggers, build steps, and post-build actions.

4. **Run the Build**: After configuring your project, you can manually trigger a build or set up automatic triggers, such as on code commits or on a scheduled basis.

5. **Monitor and Troubleshoot**: Jenkins provides a comprehensive dashboard that allows you to monitor the status of your builds, tests, and deployments. If any issues arise, you can use the built-in logging and reporting features to troubleshoot and address them.


# Installing Jenkins

## 1. Install Jenkins on Ubuntu

To install Jenkins on an Ubuntu system, follow these steps:

1. **Update the default Ubuntu packages lists for upgrades**:

   ```
   sudo apt-get update
   ```

2. **Install OpenJDK 11**:

   ```
   sudo apt-get install openjdk-11-jdk
   ```

3. **Add the Jenkins repository and key**:

   ```
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
     /usr/share/keyrings/jenkins-keyring.asc > /dev/null
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
   ```

4. **Install Jenkins**:

   ```
   sudo apt-get update
   sudo apt-get install jenkins
   ```

5. **Start the Jenkins service**:

   ```
   sudo systemctl start jenkins.service
   ```

6. **Check the Jenkins status**:

   ```
   sudo systemctl status jenkins
   ```

7. **Configure the firewall to allow access to Jenkins**:

   ```
   sudo ufw allow 8080
   sudo ufw enable
   ```

8. **Unlock Jenkins**:

   - Browse to `http://localhost:8080`
   - Retrieve the initial admin password:

     ```
     sudo cat /var/lib/jenkins/secrets/initialAdminPassword
     ```

   - Enter the password and follow the setup wizard to complete the installation.

That's it! You now have Jenkins installed and running on your Ubuntu system.

## 2. Install Jenkins on Windows

To install Jenkins on a Windows system, follow these steps:

1. **Download the Jenkins Windows installer**:
   - Go to the [Jenkins Downloads page](https://www.jenkins.io/download/) and select the Windows installer.
   - Download the installer.

2. **Run the Jenkins Windows installer**:
   - Open the downloaded installer.
   - Click "Next" to start the installation process.
   - Select the destination folder for Jenkins and click "Next".
   - Choose whether to install Jenkins as a Windows service or run it manually. It's recommended to install it as a service.
   - If installing as a service, provide the user account credentials to run the Jenkins service.
   - Select the port number for Jenkins (default is 8080) and click "Next".
   - Review the installation settings and click "Install" to begin the installation.

3. **Unlock Jenkins**:
   - Once the installation is complete, open a web browser and go to `http://localhost:8080`.
   - The setup wizard will prompt you to enter the initial admin password.
   - Retrieve the initial admin password from the file located at `C:\Program Files\Jenkins\secrets\initialAdminPassword`.
   - Copy the password and enter it in the setup wizard.
   - Follow the remaining steps in the setup wizard to complete the installation.

That's it! You now have Jenkins installed and running on your Windows system.

Citations:
[1] https://www.jenkins.io/doc/book/installing/
[2] https://github.com/yeshwanthlm/installing-jenkins
[3] https://github.com/jenkinsci/jenkins/blob/master/README.md
[4] https://www.jenkins.io/doc/book/installing/linux/
[5] https://www.jenkins.io/doc/book/installing/windows/

## Conclusion

Jenkins is a powerful and versatile tool that can greatly improve the efficiency and reliability of your software development and deployment processes. By automating your build, test, and deployment workflows, you can focus on writing better code and delivering value to your users faster.