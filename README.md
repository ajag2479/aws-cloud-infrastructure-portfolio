# AWS Cloud Infrastructure Portfolio: Enterprise Governance & Core Architecture

Welcome to my comprehensive cloud engineering portfolio. This repository documents the end-to-end deployment, optimization, and governance of **21 hands-on infrastructure projects** in Amazon Web Services. Each implementation is strictly mapped against the **AWS Well-Architected Framework** pillars to simulate real-world production environments and validate core competencies required for the AWS Certified Cloud Practitioner (CLF-C02) track.

---

## 🚀 Portfolio Architecture & Executive Summary

This enterprise portfolio is structured into **7 operational blocks** containing 21 guided labs. It transitions programmatically from foundational cloud security boundaries to complex multi-tier network isolation and automated elasticity.

### 📁 Architectural Breakdown (21 Labs)

1. **[01-aws-iam-governance](./01-aws-iam-governance/) — Identity & Access Management (4 Labs)**
   * *Focus:* Implementing corporate identity onboarding completely isolated from the AWS Root Account.
   * *Key Deliverables:* Multi-layered console password hygiene, scaleable Role-Based Access Control (RBAC) via logical groups, compute-to-storage service communication using IAM Roles (Instance Profiles), and fine-grained declarative JSON policies to enforce the **Principle of Least Privilege (PoLP)**.

2. **[02-aws-ec2-security-groups](./02-aws-ec2-security-groups/) — Compute Infrastructure & Network Firewalls (4 Labs)**
   * *Focus:* Provisioning virtual servers and configuring host-level stateful perimeters.
   * *Key Deliverables:* Cross-platform (Linux/Windows) AMI mapping, stateful firewall policies (Security Groups) restricting management protocols, cryptographic key pair governance, and automated zero-touch bootstraphing via runtime User Data automation scripts.

3. **[03-aws-elb-asg-elasticity](./03-aws-elb-asg-elasticity/) — High Availability & Elasticity (2 Labs)**
   * *Focus:* Designing fault-tolerant, horizontally scalable infrastructure.
   * *Key Deliverables:* Multi-AZ Application Load Balancers (ALB) executing dynamic target health checks and demand-driven Auto Scaling Groups (ASG) tied to metric thresholds to handle sudden traffic spikes without operational downtime.

4. **[04-aws-s3-storage-lifecycle](./04-aws-s3-storage-lifecycle/) — Object Storage & Data Retention Compliance (3 Labs)**
   * *Focus:* Securing cloud assets and automating enterprise data lifecycles.
   * *Key Deliverables:* Strict data isolation via account-level Public Access Blocks, disaster recovery and ransomware mitigation using S3 Object Versioning, and automated cost optimization through S3 Lifecycle Rules (Standard to Glacier transitions).

5. **[05-aws-rds-database-security](./05-aws-rds-database-security/) — Managed Databases & Multi-Tier Isolation (2 Labs)**
   * *Focus:* Deploying production-ready database engines disconnected from the public internet.
   * *Key Deliverables:* Private DB Subnet Group orchestration with encryption at rest, and secure cross-tier network adjacency allowing ingress SQL traffic exclusively from authorized web servers.

6. **[06-aws-vpc-network-isolation](./06-aws-vpc-network-isolation/) — Enterprise Network Topologies (3 Labs)**
   * *Focus:* Building custom, software-defined data centers from the ground up.
   * *Key Deliverables:* Custom Virtual Private Cloud (VPC) subnetting, network segmentation through explicit Public (web-facing) and Private (backend-logic) Subnet routing tables, and secure unidirectional outbound translation via highly available NAT Gateways.

7. **[07-aws-cloudwatch-observability](./07-aws-cloudwatch-observability/) — Proactive Observability & Cloud Operations (3 Labs)**
   * *Focus:* Continuous monitoring, centralized logging frameworks, and financial guardrails.
   * *Key Deliverables:* Programmatic AWS Budgets/Billing Alarms paired with automated Amazon SNS notifications, custom high-fidelity performance dashboards, and persistent CloudWatch Log Groups for centralized audit streaming and error forensics.

---

## 🛠️ Core Well-Architected Framework Competencies Demonstrated

* **Security Pillar:** Enforcing defense-in-depth, data encryption (at rest and in transit), least privilege boundaries, and infrastructure network isolation.
* **Reliability Pillar:** Engineering multi-AZ high availability, automatic scaling capabilities, component abstraction, and point-in-time recovery strategies.
* **Cost Optimization Pillar:** Eliminating wasted cloud expenditure via tier automation and enforcing immediate operational budget visibility.
* **Operational Excellence:** Leveraging Policy-as-Code principles, bootstrap automation scripts, and continuous logging architectures.

---
*For in-depth step-by-step documentation, configuration JSON payloads, scripts, and architectural proof-of-concept validation screenshots, navigate directly to each independent directory.*
