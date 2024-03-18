# Configure the EB CLI

After installing the EB CLI, you are ready to configure your project directory and the EB CLI by running `eb init`.

## Initialize an EB CLI Project

1.First, the EB CLI prompts you to select a region. Type the number that corresponds to the region that you want to use, and then press Enter.

```bash
~/eb $ eb init
```
2.Next, provide your access key and secret key so that the EB CLI can manage resources for you.

```
You have not yet set up your credentials or your credentials are incorrect.
You must provide your credentials.
(aws-access-id): AKIAJOUAASEXAMPLE
(aws-secret-key): 5ZRIrtTM4ciIAvd4EXAMPLEDtm+PiPSzpoK
```

3.An application in Elastic Beanstalk is a resource that contains a set of application versions (source), environments, and saved configurations that are associated with a single web application. Each time you deploy your source code to Elastic Beanstalk using the EB CLI, a new application version is created and added to the list.

```
Select an application to use
1) [ Create new Application ]
(default is 1): 1
```

4.Select a platform that matches the language or framework that your web application is developed in.

```
Select a platform.
1) Node.js
2) PHP
3) Python
4) Ruby
5) Tomcat
6) IIS
7) Docker
8) Multi-container Docker
9) GlassFish
10) Go
11) Java
(default is 1): 1
```
5.Choose yes to assign an SSH key pair to the instances in your Elastic Beanstalk environment.

```
Do you want to set up SSH for your instances?
(y/n): y
```

6.Choose an existing key pair or create a new one.

```
Select a keypair.
1) [ Create new KeyPair ]
(default is 1): 1
```

Your EB CLI installation is now configured and ready to use. See Managing Elastic Beanstalk environments with the EB CLI for instructions on creating and working with an Elastic Beanstalk environment.

Advanced Configuration
Ignoring files using .ebignore
Using named profiles
Deploying an artifact instead of the project folder
Configuration settings and precedence
Instance metadata
For detailed instructions and further configurations, refer to the official [AWS documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-configuration.html).

