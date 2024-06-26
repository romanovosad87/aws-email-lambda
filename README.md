# Cognito Custom Email Lambda Function

This AWS Lambda function handles custom email messages for Amazon Cognito user pools. It decrypts verification codes, customizes email content, and sends emails to users based on various triggers.

## Prerequisites

Before using this Lambda function, ensure that you have:

- An Amazon SES account with appropriate permissions.
- AWS access key ID and secret access key for SES.
- An AWS KMS key ARN for encryption and decryption.
- Environment variables set for `AWS_SES_ACCESS_KEY_ID`, `AWS_SES_ACCESS_KEY_SECRET`, `REGION`, and `KEY_ARN`.

## Usage

1. **Decrypt Verification Code**: The `decrypt` method decrypts the verification code using the AWS KMS key provided.

2. **Send Custom Email**: The `sendEmail` method sends a custom email to the user. It decrypts the code, retrieves user email addresses, and sends templated emails using Amazon SES.

3. **Handle Cognito Events**: The `handleRequest` method listens for trigger sources such as sign-up, resend code, and forgot password events. It triggers the appropriate action to send custom emails based on the event type.

## Deployment

Deploy this Lambda function in your AWS environment and configure it to handle Cognito custom email sender triggers. Ensure proper IAM permissions are set for accessing SES and KMS.

## Environment Variables

- `AWS_SES_ACCESS_KEY_ID`: Access key ID for Amazon SES.
- `AWS_SES_ACCESS_KEY_SECRET`: Secret access key for Amazon SES.
- `REGION`: AWS region where SES and KMS resources are located.
- `KEY_ARN`: ARN of the AWS KMS key for encryption and decryption.

## Execution

1. Create a new AWS Lambda function in your AWS account.
2. Upload the JAR file containing the Lambda function code.
3. Set the environment variables mentioned in the prerequisites.
4. Configure the function to trigger on Cognito custom email sender events.

## Conclusion

This Lambda function provides a flexible solution for handling custom email messages in Amazon Cognito. 
By decrypting verification codes and customizing email content, it enhances user experience and facilitates smoother communication with users. 
Deploying this function enables seamless integration with Cognito user pools and ensures timely delivery of personalized emails.

