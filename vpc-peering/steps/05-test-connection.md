# Step 5 — Test VPC Peering Connection

1. Open **EC2 instance** in Lab VPC → get **Public IP**
2. Open a browser → paste EC2PublicIP → Inventory App loads
3. Click **Settings → Configure Database**
   - Endpoint: (from lab instructions)
   - Database: inventory
   - Username: admin
   - Password: lab-password
4. Click **Save**
5. Confirm data from database is displayed

✅ Confirms traffic flows **through VPC peering**
