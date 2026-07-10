# AWS CloudWatch CPU Utilization Alarm

This project demonstrates how to monitor an Amazon EC2 instance using AWS CloudWatch.

An alarm is configured to monitor CPU Utilization. When the CPU usage exceeds the configured threshold, CloudWatch triggers an SNS notification and sends an email alert.

**Architecture**

          +----------------+
          | EC2 Instance   |
          +----------------+
                 |
                 | CPU Metrics
                 |
        +--------------------+
        | CloudWatch Metrics |
        +--------------------+
                 |
          CPU > 30%
                 |
                 ▼
        +------------------+
        | CloudWatch Alarm |
        +------------------+
                 |
                 ▼
        +------------------+
        | SNS Topic        |
        +------------------+
                 |
                 ▼
        Email Notification


**AWS Services Used**

- Amazon EC2
- Amazon CloudWatch
- Amazon SNS
- IAM


**Features**
  
✔ Monitor EC2 CPU Utilization

✔ CloudWatch Metric

✔ CloudWatch Alarm

✔ SNS Email Notification

✔ Real-time Monitoring

✔ CPU Spike Simulation using Python



**Steps Performed**

1. Created an EC2 instance.
2. Enabled Detailed Monitoring.
3. Created an SNS Topic.
4. Subscribed an email address.
5. Confirmed SNS subscription.
6. Created a CloudWatch Alarm.
7. Set threshold to CPU Utilization > 30%.
8. Simulated CPU load using Python.
9. Verified alarm state.
10. Received email notification.



**Project Screenshots**

<img width="1880" height="850" alt="image" src="https://github.com/user-attachments/assets/4930f4d6-b186-4a70-82b7-f6d1afec2aad" />
<img width="1511" height="867" alt="image" src="https://github.com/user-attachments/assets/d986378d-0efb-4fd4-819b-ad6022d5e829" />



**CPU Spike Script**

The Python script generates artificial CPU load on the EC2 instance to trigger the CloudWatch alarm.


**Project Flow**

      Start EC2
        │
        ▼
      CloudWatch collects CPU Metrics
        │
        ▼
      CPU > Threshold
        │
        ▼
      Alarm State = ALARM
        │
        ▼
      SNS Topic
        │
        ▼
      Email Notification



**Learning Outcomes**

- Learned CloudWatch Metrics

- Learned CloudWatch Alarms

- Configured SNS Notifications

- Understood EC2 Monitoring

- Implemented Infrastructure Monitoring

- Simulated CPU Load using Python


**Future Improvements**

- Monitor Memory Utilization using CloudWatch Agent

- Trigger Auto Scaling

- Trigger Lambda Function

- Send Slack Notifications

- Monitor Disk Utilization

- Create CloudWatch Dashboard
