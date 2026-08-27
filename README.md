# AWS Security Assessment: Account Baseline Guardrails

## About The Project
This project documents a security assessment performed on a standalone AWS account using the **AWS Well-Architected Framework (Security Pillar)** and **CIS AWS Foundations Benchmark v3.0**. 

The goal of this assessment was to establish baseline account hygiene, evaluate default network and encryption configurations, and implement preventative guardrails prior to deploying operational workloads.

## Key Findings
* **Identity Governance:** Multi-Factor Authentication (MFA) is active on the account root user.
* **Storage Protection:** Account-level default EBS volume encryption was disabled.
* **Network Hygiene:** Default VPC Security Group permitted unrestricted internal self-ingress traffic.
* **Resource Scope:** Verified zero public IP exposure across active compute and storage resources; account-level S3 Block Public Access is active.

## Repository Contents
* `AWS Security Assessment .pdf` — Complete assessment report detailing risk analysis, audit methodology, and remediation steps.
* `Architecture Diagram.png` — Architectural diagram of the evaluated AWS account baseline.

## Remediation & Recommendations
1. **Enable EBS Encryption by Default:** Update EC2 regional settings to ensure all future block storage volumes are encrypted at rest.
2. **Harden Default Security Group:** Remove default inbound rules from the default VPC Security Group to enforce a strict default-deny posture.
3. **Audit Logging & Continuous Monitoring:** Enforce AWS CloudTrail multi-region management event logging and AWS Security Hub automated compliance checks.
