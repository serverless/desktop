[![Serverless Desktop AWS Lambda](https://raw.githubusercontent.com/serverless/desktop/main/resources/readme-serverless-desktop.png)](https://github.com/serverless/desktop/releases/latest)

Serverless Desktop is GUI client that provides you with tooling to easily test and invoke your deployed Serverless Framework applications.

Download it [here](https://github.com/serverless/desktop/releases/latest).

<br />
<br />

## Features

![](https://raw.githubusercontent.com/serverless/desktop/main/resources/product-screenshot.png)

- Invoke AWS Lambda functions and APIs easily
- Stream errors and logs from AWS Lambdas functions in real-time
- Save and share test events and HTTP requests
- Measure performance with duration and memory metrics
- Explore items in AWS DynamoDB tables and AWS S3 buckets
- Review policies for AWS IAM roles

<br />

## How does it work?
Serverless Desktop will list your AWS Cloudformation stacks that are deployed via the [Serverless Framework](https://github.com/serverless/serverless), and create convenient views to work with the underlying AWS resources. Cloudformation stacks created outside of the Serverless Framework are currently not supported by Desktop.

Desktop will prompt you to connect your AWS Account. This will create an IAM Role in your account, that will give Desktop periodic, temporary access credentials to perform a `list` operation on your Cloudformation Stacks, and associated AWS resources. These same credentials will be used to invoke your functions, access your DynamoDB tables, S3 buckets, and work with other resources associated with your Serverless project.

Please note that while in beta, Serverless Desktop requires an AWS IAM Role with Admin permissions for your AWS account, which it assumes to periodically perform server-side operations.  Desktop does not use long-lasting credentials.  Instead, Desktop assumes the IAM Role you provide it, creates temporary credentials via AWS STS, and uses those for each opeartion.  You control the IAM Role and can remove Desktop's access at any time.  Within the upcoming weeks, Desktop will request specific permissions, rather than Admin access.  Until then, please be aware of this behavior.

<br />


## Supported platforms
- MacOS

<br />

## Supported resources
- AWS Lambda
- AWS API Gateway
- AWS DynamoDB
- AWS S3
- AWS IAM

<br />

## Limitations
- AWS only
- The AWS Role provisioned for Desktop is currently set to Administrative permissions. This will be scoped down in the future.
- Log streaming is only supported for NodeJS runtimes

<br />

## Feedback
Feel free to create an [issue](https://github.com/serverless/desktop/issues/new) to report bugs, or request features.
