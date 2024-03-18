$ AWS Elastic Beanstalk Design
![aws-worker-diagram](https://github.com/mochigome-git/aws-architecture/assets/106659178/6de2b52f-ae47-421d-a965-f4f51a3207d0)

# AWS Elastic Beanstalk Docker Deployment

This repository contains the necessary configuration files to deploy a Docker container on AWS Elastic Beanstalk, pulling the Docker image from Docker Hub.

## Prerequisites

Before deploying your application, ensure you have the following prerequisites:

- An AWS account with permissions to create and manage Elastic Beanstalk applications.
- Docker installed on your local machine for building and testing your Docker image.
- A Docker image hosted on Docker Hub that you want to deploy on Elastic Beanstalk.
- Install Python, pip, and the EB CLI on local machine.

## Getting Started

To deploy your Docker image on Elastic Beanstalk:

1. Clone this repository to your local machine:

   ```bash
   git clone <repository_url>
   ```

2. CD to your project and command to initialize the current directory with the EB CLI

   ```bash
   eb init
   ```
   refer to [Configure the EB CLI.md](https://github.com/mochigome-git/aws-architecture/blob/main/Elastic%20Beanstalk%20Workers/EB%20CLI/Configure%20the%20EB%20CLI.md)

3. “eb init” command creates .gitignore and .elasticbeanstalk directories. Change to .elasticbeanstalk directory and check the config.yml file. You can see the general configuration of the application in the config.yml file.

   ```bash
   cd ~/<projecct_path>/.elasticbeanstalk
   cat config.yml
   ```

4. To create the environment where the application will run. Run the following command to create an environment.

   ```bash
   eb create name-of-the-application
   ```

5. The process involves archiving files in the current directory and uploading them to an S3 bucket. Then, it creates an environment for the application with various components like security groups, load balancers, and auto scaling groups. If needed, it adds a policy for accessing ECR repositories. After setup, you can access the application through the Elastic Beanstalk management console or by running eb open command. You can also check Docker container status by connecting to the EC2 instance. Configuration changes can be made from the management console.

   ```bash
   eb open
   ```
   
## Clean Up
Run the following command to delete your CloudFormation stack which is created by EB CLI.

   ```bash
   eb terminate
   ```

You also need to delete the ECR repositories from CLI or AWS Management Console.

   ```bash
   aws ecr delete-repository --repository-name <app_name> --force 
   aws ecr delete-repository --repository-name <app_name> --force
   ```
