

Secure EC2 Access with PuTTY and Keypairs

📌 Overview
This project demonstrates how to securely connect to an AWS EC2 instance using PuTTY on Windows. It covers keypair conversion, PuTTY configuration, troubleshooting, and successful SSH login.

---

🚀 Steps

1. Launch EC2 Instance
- AMI: Amazon Linux 2023  
- Instance Type: t3.micro  
- Key Pair: Created at launch (downloaded as .pem)  
- Security Group: Inbound rule allowing SSH (port 22) from your IP  

2. Convert Keypair to PuTTY Format
`text
PuTTYgen → Load .pem → Save private key as .ppk
`

3. Configure PuTTY
- Session Tab  
  - Host Name: Public IPv4 (e.g., xx.xxx.xxx.xx)  
  - Port: 22  
  - Connection type: SSH  
- Connection > SSH > Auth  
  - Browse and select .ppk file  
- Save session for reuse  

4. Connect to Instance
`bash

PuTTY prompt
login as: ec2-user
`
Verify login:
`bash
whoami
uname -a
`

5. Post-Login Setup
`bash
sudo yum update -y
sudo yum install git -y
curl ifconfig.me
`

---

🔑 Key Learnings
- Match AMI type with correct default username (ec2-user for Amazon Linux, ubuntu for Ubuntu).  
- Convert .pem to .ppk for PuTTY compatibility.  
- Save PuTTY sessions to avoid re-importing keys.  
- Configure security groups correctly for SSH access.  

---

🎯 Portfolio Value
This project demonstrates:
- Practical AWS EC2 setup and secure access  
- Hands-on troubleshooting of SSH authentication errors  
- Clear, step-by-step documentation skills   

---


---

