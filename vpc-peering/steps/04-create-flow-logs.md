# Step 4 — Create VPC Flow Logs

1. In **VPC → Your VPCs**, select **Shared VPC**
2. Bottom panel → **Flow Logs → Create Flow Log**
3. Configure:
   - Name: `SharedVPCLogs`
   - Maximum aggregation interval: 1 minute
   - Destination: **CloudWatch Logs**
   - Log Group: `ShareVPCFlowLogs` (create new)
   - IAM Role: `vpc-flow-logs-Role`
4. Click **Create Flow Log**
5. Wait a few minutes, then check the log group in CloudWatch
