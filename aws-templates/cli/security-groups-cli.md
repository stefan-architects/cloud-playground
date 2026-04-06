## ✨ Placeholder Reference

| Placeholder        | Description                                                    |
|--------------------|----------------------------------------------------------------|
| `<GROUP_NAME>`     | Name of the security group to create                            |
| `<DESCRIPTION>`    | Description for the security group                              |
| `<VPC_ID>`         | ID of the VPC where the security group will be created          |
| `<PROTOCOL>`       | Network protocol to allow (e.g., `tcp`, `udp`, `icmp`)          |
| `<PORT>`           | Port number to allow for inbound traffic                        |
| `<CIDR>`           | CIDR block allowed to access the security group                 |
| `<RESOURCES>`      | Resource ID(s) to tag (for example, a security group ID)        |
| `<KEY>`            | Tag key                                                         |
| `<VALUE>`          | Tag value                                                       |

📌 **Replace all placeholder values with your own values before running the commands.**

----

## 🏗️ Create Security Group and Ingress

### 🧰 Security Group
```bash
aws ec2 create-security-group \
  --group-name <GROUP_NAME> \
  --description <DESCRIPTION> \
  --vpc-id <VPC_ID>
```

### 🧰 Authorize Ingress
```bash
aws ec2 authorize-security-group-ingress \
  --group-name <GROUP_NAME> \
  --protocol <PROTOCOL> \
  --port <PORT> \
  --cidr <x.x.x.x/x>
```
----

## 🗑️ Delete Security Group and Ingress

### 💥 Revoke Ingress
```bash
aws ec2 revoke-security-group-ingress \
  --group-name <GROUP_NAME> \
  --protocol <PROTOCOL> \
  --port <PORT> \
  --cidr <x.x.x.x/x>
```

### 💥 Security Group
```bash
aws ec2 delete-security-group \
  --group-name <GROUP_NAME>
```