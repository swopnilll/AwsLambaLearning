# Serverless Framework AWS Lambda Project

This project demonstrates how to use the Serverless Framework to create, deploy, manage, and debug AWS Lambda functions.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Creating a Lambda Function](#creating-a-lambda-function)
- [Deploying the Lambda Function](#deploying-the-lambda-function)
- [Testing the Lambda Function](#testing-the-lambda-function)
- [Resources](#resources)
- [License](#license)

## Introduction

The Serverless Framework simplifies the process of working with AWS Lambda and other cloud services. It abstracts away much of the complexity involved in creating, deploying, managing, and debugging Lambda functions by leveraging AWS CloudFormation.

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (Download and install the LTS version)
- npm (Node Package Manager, comes with Node.js)

## Installation

1. **Install Serverless Framework globally:**

   ```sh
   npm install -g serverless
   ```

2. **Verify installation:**

   ```sh
   serverless
   ```

   You should see the Serverless welcome message and available commands.

## Configuration

### AWS Credentials

To interact with AWS services, you need to configure your AWS credentials.

1. **Create an IAM user in the AWS Management Console:**

   - Go to the IAM service.
   - Create a new user (e.g., `serverless-admin`) with programmatic access.
   - Attach the `AdministratorAccess` policy to the user.
   - Download the access key ID and secret access key.

2. **Configure Serverless with your AWS credentials:**

   ```sh
   serverless config credentials --provider aws --key YOUR_ACCESS_KEY_ID --secret YOUR_SECRET_ACCESS_KEY --profile serverless-admin
   ```

   Replace `YOUR_ACCESS_KEY_ID` and `YOUR_SECRET_ACCESS_KEY` with your actual AWS credentials.

## Creating a Lambda Function

1. **Create a new Serverless project:**

   ```sh
   serverless create --template aws-nodejs --path my-service
   ```

2. **Navigate into the project directory:**

   ```sh
   cd my-service
   ```

3. **Install project dependencies:**

   ```sh
   npm install
   ```

## Deploying the Lambda Function

1. **Deploy the project to AWS:**

   ```sh
   serverless deploy
   ```

   This command packages your code, uploads it to AWS, and sets up the necessary AWS resources using CloudFormation.

## Testing the Lambda Function

1. **Invoke the function:**

   ```sh
   serverless invoke -f functionName
   ```

2. **View the logs:**

   ```sh
   serverless logs -f functionName
   ```

## Resources

- [Serverless Framework Documentation](https://www.serverless.com/framework/docs/)
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
