# 🚀 AWS Multi-VPC Architecture with VPC Peering

## 📌 Project Overview

This project demonstrates the implementation of a multi-VPC architecture in AWS with secure cross-VPC communication using VPC Peering. 

Two separate environments were created:
- Test Environment
- Production Environment

Each VPC contains public and private subnets with EC2 instances deployed inside them. VPC Peering is configured to enable private communication between both VPCs.

---

## 🏗️ Architecture Details

### 🔹 VPC 1: Test VPC
- CIDR Block: 10.0.0.0/16
- 1 Public Subnet
- 1 Private Subnet
- 1 EC2 Instance (Public)
- 1 EC2 Instance (Private)
- Internet Gateway attached

### 🔹 VPC 2: Production VPC
- CIDR Block: 192.168.0.0/16
- 1 Public Subnet
- 1 Private Subnet
- 1 EC2 Instance (Public)
- 1 EC2 Instance (Private)
- Internet Gateway attached

---

## 🔗 VPC Peering Configuration

A VPC Peering connection was established between Test and Production VPCs.

### Route Table Configuration:

- Test VPC route table updated with:
  - 192.168.0.0/16 → VPC Peering Connection

- Production VPC route table updated with:
  - 10.0.0.0/16 → VPC Peering Connection

This allowed private communication between EC2 instances in both VPCs.

---

## 🔐 Security Configuration

- Security Groups configured to allow:
  - SSH (Port 22)
  - ICMP (Ping)
- Public Subnets configured with Internet Gateway access
- Private Subnets restricted from direct internet exposure

---

## 🛠️ Implementation Steps

1. Created two VPCs (Test and Production)
2. Created public and private subnets in each VPC
3. Attached Internet Gateway to both VPCs
4. Created and configured route tables
5. Launched EC2 instances in public and private subnets
6. Created VPC Peering connection
7. Updated route tables for cross-VPC routing
8. Verified connectivity using ping between instances

---

## ✅ Validation

- Successfully pinged EC2 instances across VPCs
- Verified routing and security group configurations
- Confirmed secure private communication without internet dependency

---

## 📸 Architecture Diagram

![Architecture](architecture-diagram.png)

---

## 📂 Project Structure

```
aws-vpc-peering-project/
│
├── README.md
├── architecture-diagram.png
└── screenshots/
    ├── vpc-created.png
    ├── subnets.png
    ├── route-tables.png
    ├── peering-connection.png
    ├── security-group.png
    └── ping-success.png
```

---

## 🎯 Key Learning Outcomes

- VPC design and network segmentation
- Public vs Private subnet configuration
- Route table management
- Internet Gateway setup
- Security Group configuration
- VPC Peering implementation
- Cross-VPC private communication
