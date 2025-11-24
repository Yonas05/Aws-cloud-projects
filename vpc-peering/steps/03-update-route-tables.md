# Step 3 — Update Route Tables

### Lab VPC Public Route Table:
1. Select **Lab Public Route Table**.
2. Go to **Routes → Edit routes → Add route**:
   - Destination: `10.5.0.0/16` (Shared VPC CIDR)
   - Target: Peering Connection `Lab-Peer`
3. Save routes

### Shared VPC Route Table:
1. Select **Shared-VPC Route Table**
2. Go to **Routes → Edit routes → Add route**:
   - Destination: `10.0.0.0/16` (Lab VPC CIDR)
   - Target: Peering Connection `Lab-Peer`
3. Save routes

✅ Both VPCs can now route traffic to each other.
