Java Application Deployment with Jenkins Pipeline
Testing

This project demonstrates a CI/CD pipeline using Jenkins to build and deploy a Java application. The source code is stored in Bitbucket, built with Maven, and deployed to an Apache Tomcat server. The deployment architecture includes Nginx as a reverse proxy and MySQL as the database.

Architecture
Source Control: Bitbucket for version control.
Build Tool: Maven for compiling and packaging.
CI/CD Tool: Jenkins to automate the pipeline.
Application Server: Apache Tomcat for deployment.
Web Proxy: Nginx as a reverse proxy.
Database: MySQL for data persistence.
Pre-Requisites
Jenkins installed and configured on a dedicated server.
Apache Tomcat (8.x or later) with user access configured.
Nginx installed for proxy handling.
MySQL server running for database management.
Maven and JDK 11 installed on the build server.
Bitbucket repository containing Java source code.
Pipeline Configuration
Jenkins Setup
Install Required Plugins:

Copy Artifact
Deploy to Container
Add Credentials:

Bitbucket credentials
Tomcat user credentials for deployment
Build Job
Clone the repository from Bitbucket.
Build the application using:
bash
Copy code
mvn package
Archive the generated .war file.
Trigger the deployment job upon a successful build.
Deployment Job
Retrieve the artifact from the build job.
Deploy the .war file to Tomcat using the Deploy to Container plugin.
Validation
Commit changes to the Bitbucket repository and verify the webhook triggers Jenkins.
Ensure the application is accessible through Nginx from the public URL.
Confirm database connectivity by running the application features.
