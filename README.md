# codetech-task2
CloudWatch Monitoring and Logging Project
Project Overview
This project focuses on utilizing AWS CloudWatch to monitor and log AWS resources, providing insights into system performance and operational health. The goal is to set up CloudWatch for tracking the status of various resources such as EC2 instances, RDS databases, and other AWS services. The project also includes creating CloudWatch Alarms to trigger actions based on specific thresholds and performance metrics.

Features
Resource Monitoring: Tracks the performance and health of EC2 instances, RDS databases, and custom metrics.
Log Management: Collects and analyzes log data from AWS resources like Lambda, EC2, and more.
CloudWatch Alarms: Configures alarms to trigger notifications or actions when specified thresholds are exceeded.
Dashboard Setup: Creates CloudWatch Dashboards for visualizing the status and metrics of various AWS resources.
Automation and Alerts: Integrates CloudWatch with SNS for automatic email or SMS alerts when issues occur.
Technologies Used
AWS CloudWatch: For monitoring and logging.
AWS EC2: To launch instances for monitoring.
AWS RDS: For monitoring database performance.
AWS Lambda: For serverless computation.
Amazon SNS: For sending notifications.
AWS CloudFormation: For automating resource provisioning.
AWS IAM: For managing user access and permissions.
Setup Instructions
Pre-requisites
An AWS account.
Access to AWS Management Console.
Basic knowledge of AWS services like EC2, RDS, and Lambda.
Steps to Implement
Create EC2 Instances:

Launch EC2 instances in your AWS account.
Install necessary monitoring agents on your instances if required.
Set Up CloudWatch Logs:

Create log groups and log streams for different resources in CloudWatch.
Configure your AWS resources (EC2, RDS, Lambda) to send logs to CloudWatch.
Configure Alarms:

Set up CloudWatch Alarms for specific metrics (e.g., CPU usage, memory usage).
Set alarm thresholds to trigger notifications when limits are exceeded.
Create CloudWatch Dashboards:

Build custom dashboards to display real-time metrics for your resources (EC2, RDS).
Add widgets to the dashboard for better visualization of system health and performance.
Set Up SNS Notifications:

Configure Amazon SNS to send email or SMS notifications when alarms are triggered.
Subscribe to your SNS topics to receive alerts.
Automate Monitoring Setup (Optional):

Use AWS CloudFormation to automate the provisioning of CloudWatch resources, alarms, and dashboards.
CloudWatch Insights (Optional)
Utilize CloudWatch Logs Insights to query logs for detailed troubleshooting and analysis.
Example of CloudWatch Alarm
Here’s an example of setting up an alarm for high CPU usage on an EC2 instance:

Create an Alarm:

bash
Copy
Edit
aws cloudwatch put-metric-alarm --alarm-name "High-CPU-Alarm" --metric-name "CPUUtilization" --namespace "AWS/EC2" --statistic "Average" --period 300 --threshold 80 --comparison-operator "GreaterThanThreshold" --dimensions "Name=InstanceId,Value=i-1234567890abcdef0" --evaluation-periods 2 --alarm-actions arn:aws:sns:us-east-1:123456789012:MyTopic --ok-actions arn:aws:sns:us-east-1:123456789012:MyTopic --unit "Percent"
Set Action to Notify:

Use SNS to notify when the alarm state changes (from OK to ALARM).

