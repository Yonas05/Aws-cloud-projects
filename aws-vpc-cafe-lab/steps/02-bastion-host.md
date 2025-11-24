# Step 1 — Create Public Subnet & Internet Gateway

📸 Screenshot

**Instructions:**

1. Open the Amazon VPC console.
2. Select the Lab VPC.
3. Create a Public Subnet:
   - Name: Public Subnet
   - CIDR: 10.0.0.0/24
   - Availability Zone: <your AZ, e.g., us-east-1a>
4. Create a new Internet Gateway:
   - Name: Lab-IGW
   - Attach to Lab VPC
5. Update the Route Table for the Public Subnet:
   - Destination: 0.0.0.0/0
   - Target: Internet Gateway

**Expected Outcome:**
- Public subnet created
- Internet gateway attached
- Public subnet can route traffic to internet
# Step 2 — Launch Bastion Host in Public Subnet

📸 Screenshot

**Instructions:**

1. Open the EC2 console.
2. Launch a new EC2 instance:
   - Name: Bastion Host
   - AMI: Amazon Linux 2023
   - Instance type: t2.micro
   - Subnet: Public Subnet
   - Auto-assign public IP: Enabled
   - Key pair: vockey
3. Create a Security Group (Bastion Host SG):
   - Inbound: SSH (22) from My IP only

**Expected Outcome:**
- Bastion Host running in Public Subnet
- Accessible via SSH only from your IP
