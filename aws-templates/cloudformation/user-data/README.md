# 🌀 User Data Script

A playful EC2 demo that installs Apache, jq, and cowsay, then generates a dynamic webpage with a random personality, mood, color theme, emoji, and quote on every boot. Each reboot gives the instance a brand‑new identity.

> **Note:** This project uses the standard prerequisites and cost considerations documented in the main repository.

---

# 🚀 Deployment

### Option 1 — AWS CLI

    aws cloudformation deploy \
      --template-file user-data-script.yaml \
      --stack-name UserDataScript \
      --capabilities CAPABILITY_NAMED_IAM \
      --parameter-overrides KeyPairName=YOUR_KEYPAIR

### Option 2 — CloudFormation Console  
1. Open CloudFormation  
2. Create Stack → With new resources  
3. Upload the template  
4. Enter your KeyPair name  
5. Launch  

---

# 🏗️ Architecture Overview

This stack deploys:
- **EC2 instance** (Amazon Linux 2)  
- **Security group** (HTTP 80, SSH 22)  
- **User Data Script** that:
  - Installs Apache, jq, cowsay  
  - Generates random personality, mood, emoji, color, and quote  
  - Builds a themed webpage  
  - Logs output to `/var/log/chaos.log`  

---

# 🌀 Script Behavior

On each boot, the script:
- 🎭 Creates a random personality  
- 🎨 Generates a themed webpage (color, emoji, quote, mood)  
- 🐄 Logs chaos using cowsay  
- 🔄 Reinvents itself on every reboot  

---

# 🌐 Accessing the Webpage

After deployment:
1. Open the stack’s **Outputs**  
2. Copy `UserDataScriptURL`  
3. Open it in your browser  

---

# 🧪 Testing

Reboot the instance to generate a new identity:

    aws ec2 reboot-instances --instance-ids i-xxxxxxxxxxxx

Refresh the webpage to see the new personality.

---

# 🧹 Cleanup

To avoid charges:
1. Open CloudFormation  
2. Select `UserDataScript`  
3. Click **Delete**  

If deletion fails, remove the EC2 instance manually and retry.

---

## ⚠️ Note on AI Assistance

This user data script was generated with the help of AI. Any unexpected chaos, personality shifts, or unexplainable goblin‑like behavior is therefore completely on‑brand.

---