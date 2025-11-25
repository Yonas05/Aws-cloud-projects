# Step 9 — Create Custom Network ACL

### Create NACL  
- Name: **Lab Network ACL**
- VPC: **Lab VPC**

### Allow all traffic for Private Subnet  
Inbound: ALLOW 0.0.0.0/0  
Outbound: ALLOW 0.0.0.0/0  

Associate NACL with **Private Subnet**.

![ACL Create](../screenshots/step-15-acl-create.png)
