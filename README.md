**📦 Archived - This repository is archived and preserved for reference only. No updates, issues, or pull requests will be accepted. If you have questions, please reach out to our support team.**

---

[![Serverless Desktop AWS Lambda](https://raw.githubusercontent.com/serverless/desktop/main/resources/readme-serverless-desktop.png)](https://github.com/serverless/desktop/releases/latest)

Serverless Desktop is GUI application that makes it easier to explore and test Serverless Framework applications built on AWS Lambda.

### [Download Serverless Desktop](https://github.com/serverless/desktop/releases/latest)

Serverless Desktop is currently in beta and we are seeking customer feedback. To help us build something you love, [please take 2 minutes to answer these 4 questions](https://xv4b63nuizx.typeform.com/to/RC5jemCU).

<br />
<br />

## Features

![](https://raw.githubusercontent.com/serverless/desktop/main/resources/product-screenshot.png)

- Invoke AWS Lambda functions and APIs easily
- Stream errors and logs from AWS Lambda functions in real-time
- Save and share test events and HTTP requests
- Measure performance with duration and memory metrics
- Explore items in AWS DynamoDB tables and AWS S3 buckets
- Review policies for AWS IAM roles

<br />

## How does it work?

Serverless Desktop will list your AWS Cloudformation stacks that are deployed via the [Serverless Framework](https://github.com/serverless/serverless), and create convenient views to work with the underlying AWS resources. Cloudformation stacks created outside of the Serverless Framework are currently not supported by Desktop.

Desktop will prompt you to connect your AWS Account. This will create an IAM Role in your account, that will give Desktop periodic, temporary access credentials to perform a `list` operation on your Cloudformation Stacks, and associated AWS resources. These same credentials will be used to invoke your functions, access your DynamoDB tables, S3 buckets, and work with other resources associated with your Serverless project.

Please note that while in beta, Serverless Desktop requires an AWS IAM Role with permissions for your AWS account, which it assumes to periodically perform server-side operations.
Specifically:

- S3
- Dynamo
- Lambda
- API Gateway
- CloudFormation
- CloudWatch
- IAM (only ListRolePolicies and GetRolePolicy)

Desktop does not use long-lasting credentials. Instead, Desktop assumes the IAM Role you provide it, creates temporary credentials via AWS STS, and uses those for each operation. You control the IAM Role and can remove Desktop's access at any time. Within the upcoming weeks, Desktop will request specific permissions, rather than full read/write access. Until then, please be aware of this behavior.

Log streaming is enabled for NodeJS Lambda functions via the [AWS Lambda Extensions API](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-extensions-api.html). When you navigate to a function event trigger (HTTP, direct invocation, etc.) Desktop will add a [Lambda Layer](https://docs.aws.amazon.com/lambda/latest/dg/configuration-layers.html) to your function to capture log output. Additionally, the following environment variables are added to your Lambda:

- `AWS_LAMBDA_EXEC_WRAPPER` - The path to the Extension entrypoint
- `SERVERLESS_PLATFORM_CONFIG` - Configuration for your Serverless user and org
- `SERVERLESS_PLATFORM_DEV_MODE` - Toggles on/off log streaming

<br />

## Supported platforms

- MacOS
- Windows

<br />

## Supported regions
- us-east-1
- us-east-2
- us-west-2
- eu-central-1
- eu-west-1
- eu-west-2
- eu-west-3
- eu-north-1
- ap-northeast-1
- ap-northeast-2
- ap-southeast-1
- ap-southeast-2
- ap-south-1
- ca-central-1
- sa-east-1
- us-west-1

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
- Log streaming is only supported for NodeJS runtimes

<br />

## Feedback

Feel free to create an [issue](https://github.com/serverless/desktop/issues/new) to report bugs, or request features.
