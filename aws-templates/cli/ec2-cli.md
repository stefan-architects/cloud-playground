## ✨ Placeholder Reference
Replace the placeholder values with your own values

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<AMI_ID>`           | AMI ID to launch (e.g., Amazon Linux 2, Windows, Ubuntu, etc.)  |
| `<INSTANCE_TYPE>`    | EC2 instance type (e.g., t2.micro, t3.micro, etc.)              |
| `<SUBNET_ID>`        | Subnet where the instance will run                              |
| `<SECURITY_GROUP_ID>`| Security group ID applied to the instance                       |
| `<KEY_NAME>`         | EC2 key pair name (required to decrypt Windows admin password)  |
| `<OUTPUT_FORMAT>`    | Optional output format (default: `table`)                       |
| `<COLOR_MODE>`       | Optional color mode (default: `on`)                             |

### 🧰 Launch an EC2 Instance
```bash
aws ec2 run-instances \
  --image-id <AMI_ID> \
  --instance-type <INSTANCE_TYPE> \
  --subnet-id <SUBNET_ID> \
  --security-group-ids <SECURITY_GROUP_ID> \
  --key-name <KEY_NAME> \
  --output <OUTPUT_FORMAT> \
  --color <COLOR_MODE>
```

----

## 🗑️ Terminate the EC2 Instance

### 💥 Find the Instance ID
```bash
aws ec2 describe-instances
```

### 💥 Terminate the Instance with the Instance ID 
```bash 
aws ec2 terminate-instances \
  --instance-ids <INSTANCE_ID>
```