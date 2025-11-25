# ☕ Café VPC Lab

This project demonstrates creating a **secure VPC networking environment** for a café application in AWS, including public/private subnets, bastion host, NAT gateway, private EC2 instance, and custom network ACLs.

---

## Lab Objectives
- Create a public and private subnet
- Launch a bastion host and private EC2 instance
- Configure a NAT gateway for outbound internet access from the private subnet
- Use SSH passthrough (agent forwarding) for private instance access
- Implement a custom network ACL to control traffic
- Test connectivity and internet access

---

## Architecture Diagram
![Café VPC Architecture](aws-vpc-cafe-architecture.png)

---

## Steps

1. [Create Public Subnet & Internet Gateway](steps/01-public-subnet.md)  
   ![Step 1](screenshoots/step-01-public-subnet.png)

2. [Launch Bastion Host in Public Subnet](steps/02-bastion-host.md)  
   ![Step 2](screenshoots/step-04-bastion-ec2.png)

3. [Test SSH Connection to Bastion Host](steps/03-ssh-bastion.md)  
   ![Step 3](screenshoots/step-06-ssh-bastion.png)

4. [Create Private Subnet](steps/04-private-subnet.md)  
   ![Step 4](screenshoots/step-07-private-subnet.png)

5. [Create NAT Gateway & Private Route Table](steps/05-nat-gateway.md)  
   ![Step 5](screenshoots/step-08-nat-gateway.png)

6. [Launch Private EC2 Instance](steps/06-private-ec2.md)  
   ![Step 6](screenshoots/step-11-private-ec2.png)

7. [Enable SSH Passthrough (Agent Forwarding)](steps/07-ssh-passthrough.md)  
   ![Step 7](screenshoots/step-12-ssh-agent.png)

8. [Test Internet Access from Private Instance](steps/08-ping-private.md)  
   ![Step 8](screenshoots/step-14-ping-private.png)

9. [Create Custom Network ACL](steps/09-network-acl.md)  
   ![Step 9](screenshoots/step-15-acl-create.png)

10. [Test ACL by Blocking ICMP](steps/10-acl-test.md)  
    ![Step 10](screenshoots/step-18-acl-deny-icmp.png)

---

## screenshoots
All screenshoots of the lab steps are stored in the `screenshoots/` folder.

Example naming convention:

