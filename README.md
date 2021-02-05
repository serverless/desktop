![](https://raw.githubusercontent.com/serverless/desktop/main/resources/readme-serverless-desktop.png)

Serverless Desktop is GUI client that provides you with tooling to easily test and invoke your deployed Serverless projects.

Download it [here](https://github.com/serverless/desktop/releases/latest).

<br />
<br />

## Features

![](https://raw.githubusercontent.com/serverless/desktop/main/resources/product-screenshot.png)

- Real-time log and error streaming for AWS Lambda functions
- Saved queries
- Directly invoke AWS Lambda functions
- HTTP triggers
- Simple metrics to show memory usage, function duration, request, and response
- S3 bucket viewer
- Simple DynamoDB table query tool and viewer
- IAM policy viewer

<br />

## How does it work?
Desktop will list your AWS Cloudformation stacks that are deployed via the [Serverless Framework](https://github.com/serverless/serverless), and create convenient views to work with the underlying AWS resources. Cloudformation stacks created outside of the Serverless Framework, are currently not supported by Desktop.

Desktop will prompt you to connect your AWS Account. This will create an IAM Role in your account, that will give Desktop periodic, temporary access credentials to perform a `list` operation on your Cloudformation Stacks, and associated AWS resources. These same credentials will be used to invoke your functions, access your DynamoDB tables, S3 buckets, and work with other resources associated with your Serverless project.

<br />


## Supported platforms
MacOS

<br />

## Supported AWS resources
- Lambda
- API Gateway
- DynamoDB
- S3
- IAM

<br />

## Limitations
- AWS only
- The AWS Role provisioned for Desktop is currently set to Administrative permissions. This will be scoped down in the future.
- Log streaming only supported for NodeJS runtimes

<br />

## Feedback
Feel free to create an [issue](https://github.com/serverless/desktop/issues/new) to report bugs, or request features.
