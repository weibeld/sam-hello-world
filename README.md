# SAM Hello World

This repository contains a sample AWS Lambda application defined with the AWS [Serverless Application Model (SAM)](https://github.com/awslabs/serverless-application-model).

![AWS SAM](sam.png)

## Application

The sample application provides a REST API (with API Gateway) with a single endpoint. When this endpoint is requested, a Lambda function is triggered, which sends an email to you via the Simple Notification Service (SNS).

![Application](figures/sam-hello-world-3.png)

## Stages

This repository contains three AWS Lambda applications, where each application is a stage of the final application:

- [sam-hello-world-1](sam-hello-world-1)
- [sam-hello-world-2](sam-hello-world-2)
- [sam-hello-world-3](sam-hello-world-3)

The third stage in [sam-hello-world-3](sam-hello-world-3) is the final application, and the others are intermediate stages that you would go through when developing the final application. These intermediate stages are included here for learning purposes.

You can deploy each stage as an independent Lambda application to AWS, as described in the following.

## Deploy

You can deploy the application to AWS with the [SAM CLI](https://github.com/awslabs/aws-sam-cli):

~~~bash
sam package \
  --template-file template.yml \
  --output-template-file package.yml \
  --s3-bucket <MY_BUCKET>

sam deploy \
  --template-file package.yml \
  --stack-name <MY_STACK> \
  --capabilities CAPABILITY_IAM
~~~

You have to provide the name of an existing AWS S3 bucket in your account to the `sam package` command. The `sam package` command uploads the application artefacts (in this case the Lambda function code) to this bucket. When you later trigger a deployment with the `sam deploy` command, AWS gets the artefacts from this bucket.

For installing he SAM CLI, use the following:

~~~bash
pip install aws-sam-cli
~~~

## Article

This is an accompanying code repository of the following article:

> [Creating AWS Lambda Applications With SAM](https://medium.com/@weibeld/creating-aws-lambda-applications-with-sam-dd13258c16dd)
