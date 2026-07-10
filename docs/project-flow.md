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
