# Install CloudWatch Agent Script

#!/bin/bash
sudo yum install amazon-cloudwatch-agent -y

# Start CloudWatch Agent Command

sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
 -a fetch-config \
 -m ec2 \
 -s \
 -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json

# Check Agent Status

sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
 -a status

# Stress Test Script

#!/bin/bash
sudo yum install stress -y
stress --cpu 2 --timeout 300
