# Setup Guide

## Prerequisites

- AWS Account
- IAM User with AdministratorAccess (or required CloudWatch, EC2, and SNS permissions)
- Amazon EC2 Instance
- Python 3 installed (for CPU spike simulation)
- AWS Management Console access

---

## Step 1: Launch an EC2 Instance

1. Log in to the AWS Console.
2. Navigate to **EC2**.
3. Launch a new EC2 instance.
4. Enable **Detailed Monitoring** (recommended).

---

## Step 2: Create an SNS Topic

1. Open **Amazon SNS**.
2. Create a Standard Topic.
3. Add your email as a subscriber.
4. Confirm the subscription from your email.

---

## Step 3: Create a CloudWatch Alarm

1. Open **CloudWatch**.
2. Go to **Alarms → Create Alarm**.
3. Select Metric:
   - EC2
   - Per Instance Metrics
   - CPUUtilization
4. Choose your EC2 instance.
5. Configure:
   - Statistic: Average
   - Period: 5 Minutes
   - Threshold: Greater than 30% (or 50%)

---

## Step 4: Configure Notifications

- Select the SNS Topic created earlier.
- Save the alarm.

---

## Step 5: Simulate High CPU Usage

SSH into the EC2 instance.

Run:

```bash
python3 cpu_spike.py
```

The script increases CPU utilization to trigger the CloudWatch alarm.

---

## Step 6: Verify Alarm

Go to:

CloudWatch → Alarms

Verify the alarm changes from:

```
OK
```

to

```
ALARM
```

---

## Step 7: Verify Email Notification

Check your email.

You should receive an AWS SNS notification indicating that the CPU utilization threshold has been exceeded.

---

## Cleanup

To avoid AWS charges:

- Delete the CloudWatch Alarm
- Delete the SNS Topic
- Terminate the EC2 Instance
