# Amazon Q CLI for CloudOps & SRE Demo

[![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![Amazon Q](https://img.shields.io/badge/Amazon%20Q-232F3E?style=for-the-badge&logo=amazon&logoColor=white)](https://aws.amazon.com/q/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Complete demo materials for showcasing Amazon Q CLI's CloudOps capabilities to SRE and CloudOps teams, based on real AWS environment testing and validation.**

## 🚀 Quick Start

### Prerequisites

- [Amazon Q CLI](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-cli.html) installed
- AWS CLI configured with appropriate permissions
- MCP servers configured (see [Setup Guide](#setup))

### Run the Demo

```bash
# Clone this repository
git clone https://github.com/timwukp/amazon-q-cli-cloudops-demo.git
cd amazon-q-cli-cloudops-demo

# Follow the setup guide
open docs/SETUP.md

# Start the demo
q chat
```

## 📋 What's Included

| File | Description | Use Case |
|------|-------------|----------|
| [`docs/DEMO_SCRIPT.md`](docs/DEMO_SCRIPT.md) | Complete 60-minute demo script | Full presentation |
| [`docs/QUICK_REFERENCE.md`](docs/QUICK_REFERENCE.md) | Executive summary & key points | Quick demos |
| [`docs/SETUP.md`](docs/SETUP.md) | Installation & configuration guide | Customer self-service |
| [`docs/TESTING_RESULTS.md`](docs/TESTING_RESULTS.md) | Technical validation details | Technical deep-dive |
| [`examples/`](examples/) | Sample queries & use cases | Hands-on practice |

## 🎯 Demo Highlights

### Proven Results
- ✅ **$233/day cost optimization** identified instantly
- ✅ **8 CloudWatch alarms** analyzed across production environment
- ✅ **40+ AWS services** managed through single interface
- ✅ **70% faster troubleshooting** through AI-powered analysis

### Real Environment Testing
- **Daily Spend**: ~$600/day ($18K/month)
- **Resources**: 2 RDS instances, 19 Lambda functions, Redshift cluster
- **Services**: SageMaker, Kinesis, EKS, S3, and 35+ others
- **Monitoring**: Live CloudWatch alarms and metrics

## 🛠 Setup Guide

### 1. Install Amazon Q CLI

```bash
# Install Amazon Q CLI
npm install -g @aws/amazon-q-cli

# Verify installation
q --version
```

### 2. Configure MCP Servers

Required MCP servers for full demo functionality:

```json
{
  "mcpServers": {
    "cloudwatch": {
      "command": "npx",
      "args": ["@aws-labs/cloudwatch-mcp-server"]
    },
    "redshift": {
      "command": "npx", 
      "args": ["@aws-labs/redshift-mcp-server"]
    },
    "core": {
      "command": "npx",
      "args": ["@aws-labs/core-mcp-server"]
    }
  }
}
```

### 3. AWS Permissions

Ensure your AWS credentials have permissions for:
- CloudWatch (alarms, metrics, logs)
- RDS (describe instances)
- Redshift (connect, query)
- Lambda (list functions)
- Cost Explorer (get cost data)

## 📊 Demo Scenarios

### Scenario 1: Cost Optimization
**Query**: `"Analyze my AWS costs and identify optimization opportunities"`

**Expected Results**:
- Immediate identification of top spending services
- Specific optimization recommendations with dollar amounts
- ROI calculations for proposed changes

### Scenario 2: Incident Response
**Query**: `"Show me all active alarms and help troubleshoot issues"`

**Expected Results**:
- Real-time alarm status across all services
- Cross-service correlation analysis
- Root cause analysis with remediation suggestions

### Scenario 3: Performance Analysis
**Query**: `"Connect to my Redshift cluster and analyze performance"`

**Expected Results**:
- Live database connectivity
- Query performance metrics
- Optimization recommendations

## 🎤 Presentation Guide

### 60-Minute Full Demo
1. **System Monitoring** (18 min) - CloudWatch alarms, multi-service health
2. **Incident Response** (18 min) - Database performance, Lambda optimization
3. **Cost Analysis** (18 min) - Spend breakdown, optimization opportunities
4. **Security & Wrap-up** (6 min) - Security posture, next steps

### 30-Minute Executive Demo
1. **Cost Optimization** (15 min) - Immediate ROI demonstration
2. **Operational Efficiency** (10 min) - Cross-service analysis
3. **Next Steps** (5 min) - Implementation roadmap

### 15-Minute Lightning Demo
1. **Cost Analysis** (8 min) - "$233/day optimization identified"
2. **Live Query Demo** (5 min) - Real-time database connectivity
3. **Call to Action** (2 min) - Pilot program proposal

## 💡 Key Value Propositions

### Immediate ROI
- **$85K annual savings** potential from SageMaker optimization
- **70% faster troubleshooting** through AI-powered analysis
- **Single interface** for 40+ AWS services

### Operational Excellence
- **Natural language queries** replacing complex CLI commands
- **Cross-service correlation** automated
- **Proactive optimization** recommendations

### Technical Depth
- **Live database connectivity** with sub-second response times
- **Real-time monitoring** across all AWS services
- **AI-powered insights** beyond traditional monitoring tools

## 🔧 Customization

### For Different Environments
1. Update cost data in [`examples/cost-analysis.md`](examples/cost-analysis.md)
2. Modify service mix in [`examples/service-queries.md`](examples/service-queries.md)
3. Adjust use cases in [`docs/DEMO_SCRIPT.md`](docs/DEMO_SCRIPT.md)

### For Different Audiences
- **C-Level**: Focus on ROI and business outcomes
- **Technical Teams**: Emphasize architecture and integration
- **Operations**: Highlight day-to-day efficiency gains

## 📈 Success Metrics

### Quantifiable Outcomes
- **Cost Savings**: $100-150/day immediate opportunities
- **Time Savings**: 70% reduction in troubleshooting time
- **Efficiency**: Single interface for multi-service operations
- **Risk Reduction**: Proactive issue identification

### Audience Engagement Indicators
- Questions about specific optimizations
- Interest in implementation timeline
- Requests for additional use cases
- Discussion of integration with existing tools

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Support

### Getting Help
- 📖 [Documentation](docs/)
- 💬 [Discussions](https://github.com/timwukp/amazon-q-cli-cloudops-demo/discussions)
- 🐛 [Issues](https://github.com/timwukp/amazon-q-cli-cloudops-demo/issues)

### Contact
- **Author**: Tim Wu ([@timwukp](https://github.com/timwukp))
- **Role**: Sr. AI/ML Specialist Solutions Architect, AWS
- **LinkedIn**: [tim-wu-7865a7b0](https://www.linkedin.com/in/tim-wu-7865a7b0/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏷 Tags

`amazon-q` `aws` `cloudops` `sre` `devops` `monitoring` `cost-optimization` `demo` `ai` `cli`

---

**⭐ Star this repository if you find it helpful!**

*Last Updated: July 2025 | Environment Tested: Production AWS account with $18K/month spend*