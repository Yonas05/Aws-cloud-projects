# Step 6 — Analyze VPC Flow Logs

1. Open **CloudWatch → Log Groups → ShareVPCFlowLogs**
2. Select the **Log Stream** (starts with eni-)
3. Observe network traffic:
   - **From IP:** EC2 instance
   - **To IP:** Database
   - **Port:** 3306 (database traffic)
   - **Action:** ACCEPT
4. Confirm the traffic pattern matches application testing
