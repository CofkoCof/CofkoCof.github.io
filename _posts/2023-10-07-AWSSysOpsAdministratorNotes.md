---
title: AWS SysOps Administrator Associate Notes
date: 2023-10-07 010:00.00 +0000
categories: [AWS,SysOpsAdministrator]
tags: [aws,sysopsadministrator,certificates,notes]
---

# EC2
## General notes
- To change EC2 instance type, you first have to stop the EC2 instance

## Network Adapters
- **ENA (Elastic Network Adapter)**: higher bandwith, lower latency...up to 100Gbps. Available only for newer instances types (for example not supported on t2.micro, but supported on t3.micro)
- **EFA (Elastic Fabric Adapter)**: Improved ENA for HPC (only for Linux), it bypasses Linux OS to improve network performance

## Placement Groups
To control the EC2 Instance placement strategy

- **Cluster**: clusters instances into a low-latency group in a single Availability Zone
- **Spread**: spreads instances across underlying hardware (max 7 instances per group per Availability Zone) – critical applications
- **Partition**: spreads instances across many different partitions (which rely on different sets of racks) within an AZ.  
Scales to 100s of EC2 instances per group
