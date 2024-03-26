# Using the Amazon ECS command line interface ([link](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ECS_CLI.html))

Amazon ECS has released AWS Copilot, a command line interface (CLI) tool that simplifies building, releasing, and operating production-ready containerized applications on Amazon ECS from a local development environment. For more information, see [Using the AWS Copilot command line interface](https://aws.amazon.com/about-aws/whats-new/2021/12/aws-copilot-cli-simplify-building-releasing-operating-production-ready-containerized-applications-amazon-ecs-local-development-environment/).

The Amazon Elastic Container Service (Amazon ECS) command line interface (CLI) provides high-level commands to simplify creating, updating, and monitoring clusters and tasks from a local development environment. The Amazon ECS CLI supports Docker Compose files, a popular open-source specification for defining and running multi-container applications. Use the ECS CLI as part of your everyday development and testing cycle as an alternative to the AWS Management Console.

The latest version of the Amazon ECS CLI only supports the major versions of Docker Compose file syntax versions 1, 2, and 3. The version specified in the compose file must be the string "1", "1.0", "2", "2.0", "3", or "3.0". Docker Compose minor versions are not supported.

The source code for the Amazon ECS CLI is available on [GitHub](https://github.com/aws/amazon-ecs-cli). This tool is no longer being actively developed.

## Installing the Amazon ECS CLI

Amazon ECS has released AWS Copilot, a command line interface (CLI) tool that simplifies building, releasing, and operating production-ready containerized applications on Amazon ECS from a local development environment. For more information, see [Using the AWS Copilot command line interface](https://aws.amazon.com/about-aws/whats-new/2021/12/aws-copilot-cli-simplify-building-releasing-operating-production-ready-containerized-applications-amazon-ecs-local-development-environment/).

The following steps demonstrate how to install the Amazon ECS CLI on your macOS, Linux, or Windows system.

### To install the Amazon ECS CLI

1. **Download the Amazon ECS CLI binary.**

    - **macOS**

    ```bash
    sudo curl -Lo /usr/local/bin/ecs-cli https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-linux-amd64-latest
    ```

    - **Linux**

    ```bash
    sudo curl -Lo /usr/local/bin/ecs-cli https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-linux-amd64-latest
    ```

    - **Windows**
    
    ```bash
    sudo curl -Lo /usr/local/bin/ecs-cli https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-linux-amd64-latest
    ```

2. **Verify the Amazon ECS CLI using PGP signatures.**

    - **Download and install GnuPG.** For more information, see the [GnuPG website](https://gnupg.org/).

3. **Create a local plain text file.** Add the following contents of the Amazon ECS PGP public key and save the file.

    ```
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: GnuPG v2

    [Public Key Contents]
    -----END PGP PUBLIC KEY BLOCK-----
    ```

4. **Import the file with the Amazon ECS PGP public key with the following command in the terminal.**

    ```bash
    gpg --import <public_key_filename.txt>
    ```

5. **Download the Amazon ECS CLI signatures.**

    ```bash
    curl -Lo ecs-cli.asc https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-linux-amd64-latest.asc
    ```

6. **Verify the signature.**

    ```bash
    gpg --verify ecs-cli.asc /usr/local/bin/ecs-cli
    ```

7. **Apply execute permissions to the binary.**

    ```bash
    sudo chmod +x /usr/local/bin/ecs-cli
    ```

8. **Verify that the CLI is working properly.**

    ```bash
    ecs-cli --version
    ```

Proceed to Configuring the Amazon ECS CLI.

> **Important:** You must configure the Amazon ECS CLI with your AWS credentials, an AWS Region, and an Amazon ECS cluster name before you can use it. For more information, see Configuring the Amazon ECS CLI.

## Configuring the Amazon ECS CLI

Amazon ECS has released AWS Copilot, a command line interface (CLI) tool that simplifies building, releasing, and operating production-ready containerized applications on Amazon ECS from a local development environment. For more information, see [Using the AWS Copilot command line interface](https://aws.amazon.com/about-aws/whats-new/2021/12/aws-copilot-cli-simplify-building-releasing-operating-production-ready-containerized-applications-amazon-ecs-local-development-environment/).
