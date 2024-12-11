S3 CSV Processor - AWS Lambda
Description
This AWS Lambda function processes CSV files uploaded to an S3 bucket. When a new file is uploaded, the function reads the content, skips the header row, and logs each line to AWS CloudWatch Logs. This function is designed to demonstrate serverless file processing.

Features
Listens to S3 bucket PUT events (file uploads).
Reads and logs the content of uploaded CSV files.
Skips the header row of the CSV file.
Provides detailed logging for testing and debugging purposes.
Technologies Used
Java: For implementation of the Lambda handler.
AWS Lambda: Serverless compute platform.
Amazon S3: Cloud storage for triggering events and storing CSV files.
AWS CloudWatch Logs: For monitoring function execution and debugging.
Setup and Installation
Prerequisites
Installed Java (JDK 8 or 11) and Maven on your system.
AWS CLI configured with access to your AWS account.
An existing S3 bucket to trigger the Lambda function.
Steps to Set Up
Clone this repository to your local system.
Build the project using Maven to generate a deployable JAR file.
Deploy the JAR file to AWS Lambda using the AWS Console or AWS CLI.
Assign necessary IAM permissions to your Lambda function.
Set up an S3 bucket event notification to trigger the Lambda function on file uploads.
How It Works
When a CSV file is uploaded to the configured S3 bucket, an event notification triggers the Lambda function.
The Lambda function reads the file from S3, processes the content line by line, and logs each line to CloudWatch Logs.
The header row of the CSV file is skipped during processing.
Deployment Instructions
Build the JAR file using Maven.
Create a Lambda function in AWS Lambda Console and upload the JAR file.
Set the appropriate IAM Role for the Lambda function:
Permission to read from S3.
Permission to write logs to CloudWatch.
Configure your S3 bucket to send event notifications for file uploads (PUT events) to your Lambda function.
Testing
Upload a CSV file to the configured S3 bucket.
Verify that the Lambda function processes the file by checking the logs in AWS CloudWatch.
Ensure that each line of the CSV file (excluding the header) is logged in CloudWatch Logs.
Error Handling
The function logs a message if no records are found in the S3 event.
If an error occurs during file processing, a detailed error message is logged in CloudWatch.
Future Enhancements
Process the CSV content and store the parsed data in a database (e.g., DynamoDB or RDS).
Support multiple file formats in addition to CSV.
Implement more advanced error handling for invalid file types or corrupted files.
