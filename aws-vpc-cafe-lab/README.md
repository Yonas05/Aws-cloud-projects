☕ AWS VPC Networking Environment for Café Application
Challenge Lab: Secure VPC with Bastion Host, Private Subnet, NAT Gateway & Network ACLs

This project demonstrates building a secure VPC environment for a café’s application using layered security, subnet isolation, and controlled administrative access.

📸 Screenshot Strategy

To maintain clear documentation, each major step contains:

📷 Screenshot Placeholder

Replace the markdown image tag:
![Screenshot Step X](screenshots/step-x.png)

Upload your screenshot to a folder named screenshots inside your repo.

Name the images like:

step-01-create-public-subnet.png
step-02-create-igw.png
step-03-route-table.png
...

1️⃣ Create Public Subnet + Internet Gateway
Step 1 — Create Public Subnet

VPC: Lab VPC

Subnet name: Public Subnet

CIDR: 10.0.0.0/24

AZ: Region "a"

📷 Screenshot:

screenshots/step-01-public-subnet.png


Step 2 — Create Internet Gateway

Name: Lab-IGW

Attach to Lab VPC

📷 Screenshot:

screenshots/step-02-internet-gateway.png


Step 3 — Update Route Table

Add route:

Destination: 0.0.0.0/0

Target: Internet Gateway

📷 Screenshot:

screenshots/step-03-route-table.png


2️⃣ Create Bastion Host in Public Subnet
Step 4 — Launch EC2 "Bastion Host"

AMI: Amazon Linux 2023

Type: t2.micro

Public IP: Enabled

Key: vockey

Subnet: Public Subnet

📷 Screenshot:

screenshots/step-04-bastion-ec2.png


Step 5 — Create Security Group "Bastion Host SG"

Inbound:

Type: SSH

Source: My IP

📷 Screenshot:

screenshots/step-05-bastion-sg.png


3️⃣ Test SSH to Bastion Host
Step 6 — SSH Connection

Command:

ssh -i labsuser.pem ec2-user@<bastion-public-ip>


📷 Screenshot:

screenshots/step-06-ssh-bastion.png


4️⃣ Create Private Subnet
Step 7 — Create Private Subnet

Name: Private Subnet

CIDR: 10.0.1.0/24

📷 Screenshot:

screenshots/step-07-private-subnet.png


5️⃣ Create NAT Gateway + Private Route Table
Step 8 — Create NAT Gateway

Subnet: Public Subnet

Allocate Elastic IP

📷 Screenshot:

screenshots/step-08-nat-gateway.png


Step 9 — Create Private Route Table

Add route:

0.0.0.0/0 → NAT Gateway

📷 Screenshot:

screenshots/step-09-private-route-table.png


6️⃣ Create Private EC2 Instance
Step 10 — Create Key Pair "vockey2"

📷 Screenshot:

screenshots/step-10-keypair-vockey2.png


Step 11 — Launch EC2 "Private Instance"

AMI: Amazon Linux 2023

Subnet: Private Subnet

SG: SSH From Bastion Host SG

📷 Screenshot:

screenshots/step-11-private-ec2.png


7️⃣ Configure SSH Passthrough (Agent Forwarding)
Step 12 — Add Keys to ssh-agent
ssh-add -K vockey.pem
ssh-add -K vockey2.pem


📷 Screenshot (Terminal):

screenshots/step-12-ssh-agent.png


Step 13 — SSH to Private Instance Through Bastion
ssh -A ec2-user@<bastion-ip>
ssh ec2-user@<private-ip>


📷 Screenshot:

screenshots/step-13-ssh-private-ec2.png


8️⃣ Test Internet Access from Private Instance
Step 14 — Ping Test
ping 8.8.8.8


📷 Screenshot:

screenshots/step-14-ping-private-instance.png


9️⃣ Create Custom Network ACL
Step 15 — Create ACL

Name: Lab Network ACL

Allow ALL for Private Subnet

📷 Screenshot:

screenshots/step-15-acl-create.png


🔟 Test ACL Blocking ICMP
Step 16 — Create "Test Instance" in Public Subnet

📷 Screenshot:

screenshots/step-16-test-instance.png


Step 17 — Ping Test Instance from Private Instance

📷 Screenshot:

screenshots/step-17-ping-test-instance.png


Step 18 — Add ACL DENY Rule for ICMP

Deny ICMP from <test-ip>/32

📷 Screenshot:

screenshots/step-18-acl-deny-icmp.png
