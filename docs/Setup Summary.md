# Setup Summary – EC2 Monitoring & Alerting

## Overview

Implemented a centralized monitoring solution for EC2 using CloudWatch Agent to collect OS-level metrics and trigger alerts via SNS.

---

## Key Steps

- Launched EC2 instance with Amazon Linux
- Attached IAM role with CloudWatchAgentServerPolicy and SSM access
- Installed CloudWatch Agent on EC2
- Configured agent to collect:
  - CPU usage
  - Memory utilization
  - Disk usage

- Published metrics to custom namespace: `KavMonitoring`

- Created CloudWatch alarms:
  - CPU > 80%
  - Memory > 80%
  - Disk > 85%

- Configured SNS topic for email alerts

- Built CloudWatch Dashboard for visualization

---

## Design Decisions

- Used CloudWatch Agent for OS-level visibility (not available by default)
- Used SNS for decoupled alerting
- Chose threshold-based alarms for simplicity and clarity
- Created custom namespace for logical separation

---

## Outcome

- Achieved real-time monitoring of EC2 instance
- Successfully triggered alerts during stress testing
- Built a scalable and production-relevant observability setup
