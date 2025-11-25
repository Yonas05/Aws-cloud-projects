# Step 8 — Test Internet Access From Private Instance

SSH into bastion → then private instance:

ssh -A ec2-user@<private-ip>

yaml
Copy code

Test outbound internet through NAT:

ping 8.8.8.8

vbnet
Copy code

![Ping Private](../screenshots/step-14-ping-private.png)