## ✨ Placeholder Reference
Replace the placeholder values with your own values

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<KEY_PAIR_NAME>` | The name you want to assign to the EC2 key pair |
| `<KEY_PAIR_TYPE>` | The key type, e.g., `rsa`, `ed25519` |
| `<OUTPUT_FILE>` | The filename (without extension) where the `.pem` key will be saved |

### 🧰 EC2 Key Pair Create
```bash
aws ec2 create-key-pair \
  --key-name <KEY_PAIR_NAME> \
  --key-type <KEY_PAIR_TYPE> \
  --query "KeyMaterial" \
  --output text > <FILE_TYPE>.pem
```