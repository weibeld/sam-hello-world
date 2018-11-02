# SAM Hello World

AWS Lambda application created with AWS [Serverless Application Model (SAM)](https://github.com/awslabs/serverless-application-model).

![AWS SAM](sam.png)

## Steps

This repository includes intermediate steps of the final application:

- [sam-hello-world-1](sam-hello-world-1)
- [sam-hello-world-2](sam-hello-world-2)
- [sam-hello-world-3](sam-hello-world-3)

## Final Application

![Final application](figures/sam-hello-world-3.png)

## Deploy

~~~bash
sam package \
  --template-file template.yml \
  --output-template-file package.yml \
  --s3-bucket <my-bucket>

sam deploy \
  --template-file package.yml \
  --stack-name <sam-hello-world-X> \
  --capabilities CAPABILITY_IAM
~~~

If necessary, install the SAM CLI as follows:

~~~bash
pip install aws-sam-cli
~~~

## Article

This is an accompanying code repository of the following article:

> [Creating AWS Lambda Applications With SAM](https://medium.com/@weibeld/creating-aws-lambda-applications-with-sam-dd13258c16dd)
