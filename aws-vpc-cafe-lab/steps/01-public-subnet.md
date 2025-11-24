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
