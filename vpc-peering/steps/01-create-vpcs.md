# Step 1 — Create VPCs

Two VPCs are used in this lab:

- **Lab VPC:** Contains EC2 with Inventory Application (Public Subnet)
- **Shared VPC:** Contains Database instance (Private Subnet)

### Steps:
1. Open the AWS Management Console → VPC.
2. Create **Lab VPC** with CIDR `10.0.0.0/16`.
3. Create **Shared VPC** with CIDR `10.5.0.0/16`.
4. Create at least one subnet in each VPC:
   - Lab VPC → public subnet
   - Shared VPC → private subnet
5. Ensure **DNS support** is enabled.
