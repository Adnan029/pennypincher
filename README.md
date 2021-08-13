## Penny Pincher - An alerting solution for Cloud Cost Optimization

### Aim 

The aim is to setup a lambda function which sends information of all the resources which are provisioned but are not being used i.e. are idle along with potential savings over email and slack.

### Features

1. Generates a report consisting of all the idle resources in the account and potential savings.
2. Two platforms are supported for receiving the report, one is email and another is slack.
3. The number of days for which resource metrics (usage) is to be monitored can be set by the end user.
4. The solution is easily deployable as the whole setup is done using AWS Cloudformation.

### Pre-requisites

1. The IAM user used to setup the lambda should have access to AWS S3, AWS IAM, AWS Lambda, AWS SES and AWS Cloudformation.
2. An AWS S3 bucket.
3. A slack workspace. (Only if cost report is to be sent on any slack channel)
4. A verified SES email Address. (Only if cost report is to be sent over email)

### Quick Setup

### Docker

To start Penny Pincher, run the following command
```bash
docker-compose up
```
### Cloudformation
1. Create an S3 bucket and upload the files code.zip and packages.zip in the bucket.
2. Create a cloudformation stack using the penny_pincher_cfn.yml template file.
3. Input the required parameters for receiving the report and create the stack
4. Go to the AWS Lambda console, select the lambda "Penny-Pincher". Click on Test button to    run the Lambda .
5. After a few minutes, you will receive the report on your email id and/or slack channel. 

For detailed instructions, refer to [Setup through Cloudformation](docs/setup_through_cloudformation.md)

### Authentication
Before launching Penny Pincher you need to configure your AWS authentication method
AWS_PROFILES
ACCESS KEY

### Advanced settings
Advanced configuration details can be found [here](docs/advanced_settings.md)


