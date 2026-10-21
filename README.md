# EWB Cloud Labs - Project 01: AWS VPC Peering

**Student:** Naga Ganesh Eswar Gangisetty | **Batch:** AWS Internship Batch 1.1 | **Region:** ap-south-1 (Mumbai) | **Date:** 21 Oct 2026

Two VPCs (10.10.0.0/16, 10.20.0.0/16) connected with a VPC peering connection. One public bastion in VPC A for administration (SSH ProxyJump); both application servers stay fully private. Proves private connectivity with a baseline failure, forward/reverse ping success, private SSH to App-B, and a controlled security-group failure with recovery. All resources were deleted after evidence capture.

- **Report:** [NagaGanesh_EWB_VPC_Peering.pdf](NagaGanesh_EWB_VPC_Peering.pdf)
- **Evidence:** console screenshots + raw terminal output in [evidence/](evidence/)

## Resource plan
| Resource | CIDR / IP |
|---|---|
| ewb-vpc-a | 10.10.0.0/16 |
| ewb-a-public | 10.10.1.0/24 (bastion 10.10.1.10) |
| ewb-a-private | 10.10.2.0/24 (App-A 10.10.2.10) |
| ewb-vpc-b | 10.20.0.0/16 |
| ewb-b-private | 10.20.1.0/24 (App-B 10.20.1.10) |
| Peering | ewb-a-b-peer, routes both ways |

Tests: baseline 100% loss before peering; 4/4 replies both ways after; SSH to App-B through bastion; ICMP rule removal stops replies, restore recovers them.
