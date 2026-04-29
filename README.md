# Centralized Monitoring & Alerting System

## Project Overview

Designed and implemented a **centralized monitoring and alerting system** for EC2 infrastructure using AWS native services.

The system continuously collects system-level metrics (CPU, Memory, Disk), visualizes them in dashboards, and triggers real-time alerts when thresholds are breached.

---

## Architecture

![Architecture](architecture/Architecture.PNG)

---

## AWS Services Used

- Amazon EC2 (Compute instance)
- Amazon CloudWatch (Metrics, Logs, Alarms, Dashboard)
- CloudWatch Agent (Custom OS-level metrics)
- Amazon SNS (Email notifications)
- AWS IAM (Secure access control)

---

## Workflow

1. EC2 instance runs continuously
2. CloudWatch Agent collects system metrics every 60 seconds
3. Metrics are pushed to CloudWatch under a custom namespace
4. CloudWatch Alarms monitor thresholds:
   - CPU > 80%
   - Memory > 80%
   - Disk > 85%

5. On breach → SNS sends real-time alert email

---

## Implementation Summary

- Launched EC2 instance (Amazon Linux)
- Configured IAM role with CloudWatch + SSM access
- Installed and configured CloudWatch Agent
- Collected custom metrics (CPU, Memory, Disk)
- Created CloudWatch alarms for proactive monitoring
- Integrated SNS for alert notifications
- Built a CloudWatch Dashboard for visualization

---

## Monitoring Dashboard

- Real-time CPU usage
- Memory utilization trends
- Disk usage metrics

---

## Testing

- Installed stress tool on EC2
- Simulated high CPU usage
- Verified:
  - Alarm state transition (OK → ALARM)
  - SNS email notification received
  - Metrics spike visible on dashboard

---

## Security Considerations

- Used IAM role instead of access keys
- Restricted inbound access (SSH only)

---

## Use Cases

- Production server health monitoring
- Infrastructure alerting systems

---

## Key Learnings

- Implemented infrastructure observability using CloudWatch
- Configured custom metrics via CloudWatch Agent
- Designed alert-driven monitoring workflows
- Integrated SNS for real-time notifications
- Built dashboards for operational visibility

---

## Author

Kavya
