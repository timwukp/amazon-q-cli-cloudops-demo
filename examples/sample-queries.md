# Sample Queries - Amazon Q CLI CloudOps

> **Collection of tested queries for hands-on practice and customization**

## 🎯 Getting Started Queries

### Basic Environment Discovery
```bash
# Get AWS account overview
"Show me my AWS account information and current region"

# List available MCP servers
"What MCP servers are available and connected?"

# Basic infrastructure overview
"Give me an overview of my AWS infrastructure"
```

---

## 📊 Cost Analysis Queries

### Daily Cost Breakdown
```bash
# Top spending services
"Analyze my AWS costs for the last 7 days and show me the top spending services"

# Cost trends
"Show me my AWS cost trends over the last 30 days"

# Service-specific analysis
"Break down my compute costs across EC2, Lambda, and EKS"
```

### Optimization Opportunities
```bash
# General optimization
"Identify cost optimization opportunities across all my AWS services"

# Specific service optimization
"Analyze my SageMaker usage and suggest cost optimization strategies"
"Review my S3 storage costs and recommend lifecycle policies"
"Examine my RDS spending and suggest right-sizing opportunities"
```

### Budget and Forecasting
```bash
# Spending patterns
"What are my biggest cost drivers and how have they changed over time?"

# Future projections
"Based on current trends, what will my monthly AWS bill be?"

# Anomaly detection
"Identify any unusual spending patterns or cost anomalies"
```

---

## 🔍 Monitoring & Observability Queries

### CloudWatch Alarms
```bash
# Active alarms
"Show me all CloudWatch alarms currently in ALARM state"

# Alarm analysis
"Analyze my alarm patterns and suggest optimization strategies"

# Historical context
"Which alarms have been in ALARM state the longest?"
```

### Log Analysis
```bash
# Log groups overview
"Show me all my CloudWatch log groups and their storage usage"

# Error pattern analysis
"Analyze error patterns in my application logs from the last 24 hours"

# Service-specific logs
"Show me recent Lambda function errors and their patterns"
"Analyze AWS Glue job logs for any failures or performance issues"
```

### Metrics and Performance
```bash
# Performance overview
"Give me a performance overview of my key AWS services"

# Resource utilization
"Show me CPU and memory utilization across my infrastructure"

# Network analysis
"Analyze network performance and data transfer costs"
```

---

## 🗄️ Database Queries

### RDS Analysis
```bash
# Instance overview
"Show me all my RDS instances and their current status"

# Performance analysis
"Analyze my RDS performance and identify any bottlenecks"

# Cost optimization
"Review my RDS configurations and suggest cost optimizations"
```

### Redshift Operations
```bash
# Cluster status
"What's the status of my Redshift clusters?"

# Live connection
"Connect to my Redshift cluster and show me available databases"

# Performance analysis
"Analyze my Redshift query performance and identify slow queries"

# Storage optimization
"Review my Redshift storage usage and suggest optimizations"
```

### Database Security
```bash
# Security configuration
"Check the security configuration of my databases"

# Access patterns
"Analyze database access patterns and identify any anomalies"

# Backup status
"Show me the backup status of all my databases"
```

---

## ⚡ Lambda & Serverless Queries

### Function Analysis
```bash
# Function overview
"List all my Lambda functions and their configurations"

# Performance analysis
"Analyze my Lambda functions for performance optimization opportunities"

# Cost analysis
"Show me the cost breakdown of my Lambda functions"
```

### Optimization Opportunities
```bash
# Runtime upgrades
"Which Lambda functions need runtime upgrades?"

# Memory optimization
"Analyze Lambda function memory usage and suggest right-sizing"

# Timeout analysis
"Review Lambda function timeouts and suggest optimizations"
```

### Error Analysis
```bash
# Error patterns
"Show me Lambda function errors from the last 7 days"

# Failure analysis
"Analyze Lambda function failures and their root causes"

# Performance issues
"Identify Lambda functions with performance issues"
```

---

## 🔒 Security & Compliance Queries

### Security Posture
```bash
# Security overview
"Analyze my AWS security posture and identify any gaps"

# Service coverage
"Show me my security service spending and coverage"

# Compliance status
"Check my infrastructure against AWS security best practices"
```

### Access Analysis
```bash
# IAM analysis
"Review my IAM policies and identify overprivileged access"

# Access patterns
"Analyze access patterns and identify any anomalies"

# Security groups
"Review my security group configurations"
```

### Threat Detection
```bash
# GuardDuty findings
"Show me any GuardDuty findings from the last 30 days"

# Security Hub alerts
"Analyze Security Hub findings and prioritize remediation"

# Config compliance
"Check AWS Config compliance across my resources"
```

---

## 🏗️ Infrastructure Queries

### Resource Inventory
```bash
# Complete inventory
"Give me a complete inventory of my AWS resources"

# Service utilization
"Show me utilization across all my AWS services"

# Unused resources
"Identify any unused or underutilized resources"
```

### Performance Analysis
```bash
# Infrastructure health
"Analyze the health of my AWS infrastructure"

# Bottleneck identification
"Identify any performance bottlenecks in my infrastructure"

# Capacity planning
"Analyze my resource usage trends for capacity planning"
```

### Optimization Recommendations
```bash
# General optimization
"Provide optimization recommendations for my entire infrastructure"

# Service-specific optimization
"Optimize my container workloads on EKS"
"Suggest improvements for my data processing pipeline"
```

---

## 🔧 Troubleshooting Queries

### Incident Response
```bash
# Current issues
"Show me any current issues or alerts across my infrastructure"

# Root cause analysis
"Help me analyze the root cause of recent performance issues"

# Impact assessment
"Assess the impact of current alarms on my services"
```

### Performance Troubleshooting
```bash
# Slow queries
"Identify slow database queries and suggest optimizations"

# High CPU usage
"Show me resources with high CPU usage and analyze the cause"

# Network issues
"Analyze network performance and identify any issues"
```

### Historical Analysis
```bash
# Trend analysis
"Analyze performance trends over the last 30 days"

# Incident patterns
"Identify patterns in my infrastructure incidents"

# Capacity trends
"Show me capacity utilization trends across services"
```

---

## 🎨 Custom Query Templates

### Environment-Specific Queries
```bash
# Replace with your specific resources
"Analyze the performance of my [SERVICE_NAME] workload"
"Show me cost optimization opportunities for my [PROJECT_NAME] infrastructure"
"Review the security configuration of my [ENVIRONMENT] resources"
```

### Time-Based Analysis
```bash
# Flexible time ranges
"Analyze my AWS costs for the last [X] days"
"Show me performance metrics from [START_DATE] to [END_DATE]"
"Identify trends over the past [TIME_PERIOD]"
```

### Service-Specific Templates
```bash
# Customize for your services
"Optimize my [SERVICE] configuration for cost and performance"
"Analyze [SERVICE] usage patterns and suggest improvements"
"Show me [SERVICE] security best practices compliance"
```

---

## 💡 Query Best Practices

### Effective Query Structure
1. **Be specific**: Include service names, time ranges, and metrics
2. **Use context**: Reference your specific environment and resources
3. **Ask for analysis**: Request insights, not just data
4. **Combine services**: Ask for cross-service correlation

### Example Improvements
❌ **Vague**: "Show me costs"
✅ **Specific**: "Analyze my AWS costs for the last 7 days and identify the top 5 spending services"

❌ **Data only**: "List my Lambda functions"
✅ **Analysis**: "Analyze my Lambda functions for optimization opportunities and cost savings"

### Follow-up Strategies
1. **Drill down**: Ask for more details on interesting findings
2. **Cross-reference**: Connect findings across different services
3. **Action-oriented**: Ask for specific recommendations and next steps

---

## 🔄 Customization Guide

### Adapting Queries for Your Environment
1. **Replace service names** with your specific resources
2. **Adjust time ranges** based on your analysis needs
3. **Add environment context** (prod, staging, dev)
4. **Include business context** (project names, team ownership)

### Creating New Queries
1. **Start with discovery**: "Show me..." or "List my..."
2. **Add analysis**: "Analyze..." or "Identify..."
3. **Request recommendations**: "Suggest..." or "Recommend..."
4. **Include context**: Time ranges, specific services, business impact

---

**💡 Pro Tip**: Start with basic discovery queries to understand your environment, then move to analysis and optimization queries for deeper insights.