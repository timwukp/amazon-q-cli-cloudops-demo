# Setup Guide - Amazon Q CLI for CloudOps

This guide will help you set up Amazon Q CLI with the necessary MCP servers to run the CloudOps demo in your own AWS environment.

## 📋 Prerequisites

### System Requirements
- **Node.js**: Version 18 or higher
- **npm**: Version 8 or higher
- **AWS CLI**: Version 2.x configured with credentials
- **Operating System**: macOS, Linux, or Windows with WSL2

### AWS Account Requirements
- Active AWS account with billing enabled
- IAM permissions for the services you want to demo
- At least some AWS resources deployed (for meaningful demo results)

## 🚀 Installation Steps

### Step 1: Install Amazon Q CLI

```bash
# Install Amazon Q CLI globally
npm install -g @aws/amazon-q-cli

# Verify installation
q --version
```

### Step 2: Configure AWS Credentials

Ensure your AWS CLI is configured with appropriate credentials:

```bash
# Configure AWS CLI (if not already done)
aws configure

# Verify access
aws sts get-caller-identity
```

### Step 3: Install Required MCP Servers

The demo requires several MCP servers. Install them using npm:

```bash
# Install CloudWatch MCP Server
npm install -g @aws-labs/cloudwatch-mcp-server

# Install Redshift MCP Server  
npm install -g @aws-labs/redshift-mcp-server

# Install Core MCP Server
npm install -g @aws-labs/core-mcp-server

# Install AWS Documentation MCP Server (optional)
npm install -g @aws-labs/aws-documentation-mcp-server
```

### Step 4: Configure MCP Servers

Create or update your Q CLI configuration file:

**Location**: 
- macOS/Linux: `~/.config/amazon-q/config.json`
- Windows: `%APPDATA%\amazon-q\config.json`

**Configuration**:
```json
{
  "mcpServers": {
    "cloudwatch": {
      "command": "npx",
      "args": ["@aws-labs/cloudwatch-mcp-server"],
      "env": {
        "AWS_REGION": "us-east-1"
      }
    },
    "redshift": {
      "command": "npx",
      "args": ["@aws-labs/redshift-mcp-server"],
      "env": {
        "AWS_REGION": "us-east-1"
      }
    },
    "core": {
      "command": "npx",
      "args": ["@aws-labs/core-mcp-server"],
      "env": {
        "AWS_REGION": "us-east-1"
      }
    },
    "documentation": {
      "command": "npx",
      "args": ["@aws-labs/aws-documentation-mcp-server"]
    }
  }
}
```

**Note**: Replace `us-east-1` with your preferred AWS region.

## 🔐 AWS Permissions

### Required IAM Permissions

Your AWS credentials need the following permissions for full demo functionality:

#### CloudWatch Permissions
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "cloudwatch:DescribeAlarms",
        "cloudwatch:GetMetricData",
        "cloudwatch:GetMetricStatistics",
        "logs:DescribeLogGroups",
        "logs:StartQuery",
        "logs:GetQueryResults",
        "logs:StopQuery"
      ],
      "Resource": "*"
    }
  ]
}
```

#### Database Permissions
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "rds:DescribeDBInstances",
        "rds:DescribeDBClusters",
        "redshift:DescribeClusters",
        "redshift-data:ExecuteStatement",
        "redshift-data:DescribeStatement",
        "redshift-data:GetStatementResult"
      ],
      "Resource": "*"
    }
  ]
}
```

#### Cost and Billing Permissions
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ce:GetCostAndUsage",
        "ce:GetUsageReport",
        "ce:GetReservationCoverage",
        "ce:GetReservationPurchaseRecommendation",
        "ce:GetReservationUtilization"
      ],
      "Resource": "*"
    }
  ]
}
```

#### Lambda and General Permissions
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "lambda:ListFunctions",
        "lambda:GetFunction",
        "ec2:DescribeInstances",
        "ec2:DescribeImages",
        "s3:ListAllMyBuckets",
        "s3:GetBucketLocation"
      ],
      "Resource": "*"
    }
  ]
}
```

### Simplified IAM Policy

For demo purposes, you can use this comprehensive policy (adjust for production use):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "cloudwatch:*",
        "logs:*",
        "rds:Describe*",
        "redshift:Describe*",
        "redshift-data:*",
        "lambda:List*",
        "lambda:Get*",
        "ec2:Describe*",
        "s3:List*",
        "s3:Get*",
        "ce:*"
      ],
      "Resource": "*"
    }
  ]
}
```

## ✅ Verification Steps

### Test Basic Functionality

1. **Start Q CLI**:
   ```bash
   q chat
   ```

2. **Test MCP Server Connection**:
   ```
   Query: "What MCP servers are available?"
   ```

3. **Test AWS Connectivity**:
   ```
   Query: "Show me my AWS account information"
   ```

4. **Test CloudWatch Integration**:
   ```
   Query: "Show me any active CloudWatch alarms"
   ```

5. **Test Cost Analysis**:
   ```
   Query: "What are my top AWS spending services?"
   ```

### Expected Results

If everything is configured correctly, you should see:
- ✅ MCP servers listed and connected
- ✅ AWS account information displayed
- ✅ CloudWatch data retrieved (alarms, metrics)
- ✅ Cost data from your AWS account

## 🛠 Troubleshooting

### Common Issues

#### MCP Server Not Found
```
Error: MCP server 'cloudwatch' not found
```
**Solution**: Ensure the MCP server is installed globally:
```bash
npm install -g @aws-labs/cloudwatch-mcp-server
```

#### AWS Permissions Error
```
Error: Access denied for operation
```
**Solution**: Check your IAM permissions and ensure your AWS credentials are configured correctly.

#### Connection Timeout
```
Error: Connection timeout
```
**Solution**: Check your network connectivity and AWS region configuration.

### Debug Mode

Enable debug mode for detailed logging:

```bash
# Set debug environment variable
export DEBUG=amazon-q:*

# Run Q CLI with debug output
q chat
```

### Log Files

Check log files for detailed error information:
- macOS/Linux: `~/.config/amazon-q/logs/`
- Windows: `%APPDATA%\amazon-q\logs\`

## 🎯 Demo Preparation

### Recommended AWS Resources

For the best demo experience, ensure you have:

1. **CloudWatch Alarms**: At least 2-3 active alarms
2. **RDS/Aurora**: At least one database instance
3. **Lambda Functions**: A few functions with recent executions
4. **Cost Data**: At least 7 days of billing history
5. **S3 Buckets**: Some storage usage for cost analysis

### Pre-Demo Checklist

- [ ] Q CLI installed and working
- [ ] All MCP servers configured and connected
- [ ] AWS credentials have required permissions
- [ ] Test queries return expected results
- [ ] Demo script reviewed and customized
- [ ] Backup queries prepared for common issues

## 🔄 Updates and Maintenance

### Keeping Components Updated

```bash
# Update Amazon Q CLI
npm update -g @aws/amazon-q-cli

# Update MCP servers
npm update -g @aws-labs/cloudwatch-mcp-server
npm update -g @aws-labs/redshift-mcp-server
npm update -g @aws-labs/core-mcp-server
```

### Configuration Backup

Keep a backup of your working configuration:

```bash
# Backup configuration
cp ~/.config/amazon-q/config.json ~/.config/amazon-q/config.json.backup
```

## 📞 Getting Help

### Support Resources
- [Amazon Q CLI Documentation](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-cli.html)
- [MCP Server Documentation](https://github.com/aws-labs/)
- [AWS CLI Configuration Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

### Community Support
- [GitHub Issues](https://github.com/timwukp/amazon-q-cli-cloudops-demo/issues)
- [GitHub Discussions](https://github.com/timwukp/amazon-q-cli-cloudops-demo/discussions)

---

**Next Steps**: Once setup is complete, proceed to the [Demo Script](DEMO_SCRIPT.md) to start your presentation!