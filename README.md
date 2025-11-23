# Project-AWS-HoneyPot
This project is an AWS honeypot designed to attract and analyze malicious traffic within a controlled environment. It uses an isolated EC2 instance with intentionally exposed ports, custom Security Group rules, and CloudWatch logging to track inbound attacks. Collected logs are analyzed to identify attacker patterns, common scanning behavior, and attempted exploit techniques.

# 🍯 AWS Cloud Honeypot Project

![Security](https://img.shields.io/badge/Security-Research-red)
![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![Status](https://img.shields.io/badge/Status-Active-green)
![License](https://img.shields.io/badge/License-MIT-blue)

## 📋 Overview

A production-grade honeypot deployment on AWS infrastructure designed to collect and analyze malicious traffic patterns, attack vectors, and threat intelligence data. This project demonstrates cloud security monitoring, threat detection, and incident response capabilities.

## 🎯 Objectives

- **Threat Intelligence Collection**: Gather real-world attack data and patterns
- **Attack Vector Analysis**: Identify common exploitation attempts and techniques
- **Security Research**: Contribute to the cybersecurity community with findings
- **Cloud Security**: Demonstrate AWS security best practices and monitoring

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                      Internet                           │
└────────────────────┬────────────────────────────────────┘
                     │
              ┌──────▼──────┐
              │   Route 53   │
              └──────┬───────┘
                     │
         ┌───────────▼────────────┐
         │   CloudFront (CDN)     │
         └───────────┬────────────┘
                     │
    ┌────────────────▼────────────────┐
    │        VPC (10.0.0.0/16)        │
    │  ┌───────────────────────────┐  │
    │  │   Public Subnet           │  │
    │  │   ┌─────────────────┐    │  │
    │  │   │  EC2 Honeypot   │    │  │
    │  │   │  Instance        │    │  │
    │  │   └────────┬────────┘    │  │
    │  └────────────┼──────────────┘  │
    │               │                  │
    │  ┌────────────▼──────────────┐  │
    │  │   CloudWatch Logs         │  │
    │  └────────────┬──────────────┘  │
    └───────────────┼──────────────────┘
                    │
         ┌──────────▼──────────┐
         │    S3 Data Lake     │
         └──────────┬──────────┘
                    │
         ┌──────────▼──────────┐
         │   Athena Analytics  │
         └─────────────────────┘
```

## 🚀 Features

- **Multi-Protocol Support**: SSH, HTTP/HTTPS, Telnet, FTP monitoring
- **Real-time Alerting**: CloudWatch alarms for suspicious activities
- **Data Analytics**: Automated analysis with AWS Athena
- **Geolocation Tracking**: IP-based attack origin mapping
- **Low Interaction Design**: Safe, contained environment
- **Automated Reporting**: Daily threat intelligence summaries

## 📊 Data Collection Metrics

- Source IP addresses and geolocation
- Attack timestamps and frequency
- Attempted credentials (username/password combinations)
- Malware samples and payloads
- Command execution attempts
- Port scanning patterns
- User-agent strings and bot signatures

## 🛠️ Technology Stack

- **Cloud Platform**: AWS (EC2, VPC, S3, CloudWatch, Athena)
- **Operating System**: Ubuntu 22.04 LTS
- **Honeypot Software**: Cowrie, Dionaea, Honeytrap
- **Monitoring**: CloudWatch, VPC Flow Logs
- **Analytics**: AWS Athena, QuickSight
- **Infrastructure as Code**: Terraform
- **CI/CD**: GitHub Actions

## 📦 Installation

### Prerequisites

- AWS Account with appropriate IAM permissions
- AWS CLI configured
- Terraform >= 1.0
- Python 3.8+
- Git

### Quick Start

```bash
# Clone the repository
git clone https://github.com/yourusername/aws-honeypot.git
cd aws-honeypot

# Configure AWS credentials
aws configure

# Initialize Terraform
cd terraform
terraform init

# Deploy infrastructure
terraform plan
terraform apply

# Deploy honeypot software
cd ../scripts
./deploy_honeypot.sh
```

## 📁 Project Structure

```
aws-honeypot/
├── terraform/              # Infrastructure as Code
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
├── scripts/               # Deployment and maintenance scripts
│   ├── deploy_honeypot.sh
│   ├── analyze_logs.py
│   └── generate_report.py
├── config/                # Configuration files
│   ├── cowrie.cfg
│   └── dionaea.conf
├── analytics/             # Data analysis notebooks
│   ├── threat_analysis.ipynb
│   └── geographic_distribution.ipynb
├── reports/               # Generated reports
│   └── daily/
└── docs/                  # Documentation
    ├── SETUP.md
    ├── SECURITY.md
    └── ANALYSIS.md
```

## 🔒 Security Considerations

- Honeypot runs in isolated VPC subnet
- Strict security group rules (ingress only for monitored ports)
- No sensitive data or production systems in the same VPC
- Regular security updates and patches
- Encrypted data storage in S3
- IAM roles with least privilege principle

## 📈 Daily Updates

Follow the project progress with daily updates on LinkedIn. Each day features:
- Attack statistics and trends
- Interesting findings and patterns
- Technical insights and lessons learned
- Visualizations and heat maps

### Week 1 Milestones
- **Day 1**: Infrastructure deployment and initial data collection
- **Day 2**: First 24-hour attack pattern analysis
- **Day 3**: Geographic distribution of threats
- **Day 4**: Most common attack vectors identified
- **Day 5**: Credential analysis and password trends
- **Day 6**: Malware samples and payload analysis
- **Day 7**: Week 1 comprehensive report and insights

## 📊 Sample Data Insights

```
Total Attacks (24h): 3,847
Unique IPs: 423
Top Countries: CN (34%), RU (18%), US (12%)
Most Targeted Port: 22/SSH (67%)
Failed Login Attempts: 2,156
Unique Passwords Tried: 892
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Additional honeypot services
- Analysis improvements
- Documentation updates
- Bug fixes

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This honeypot is for research and educational purposes only. Ensure you comply with:
- AWS Acceptable Use Policy
- Local and international laws
- Responsible disclosure practices

## 📫 Contact

- LinkedIn: linkedin.com/in/ella-tse
- GitHub: 3stella25
- Email: est69860@uga.edu, ellastse19@gmail.com

## 🙏 Acknowledgments

- AWS Security Team for best practices guidance
- The Honeynet Project for inspiration
- Open source honeypot communities

---

**⭐ If you find this project useful, please consider starring the repository!**

**Last Updated**: November 2024
**Status**: 🟢 Actively Collecting Data
