## ✨ Placeholder Reference
Replace the placeholder values with your own values

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<IAM_USER_NAME>` | The name of the IAM user you want to create or reference |
| `<IAM_GROUP_NAME>` | The name of the IAM group you want to create or reference |

## 🔧 Creating User & Group

### ✅ Create IAM User
```bash
aws iam create-user \
  --user-name <IAM_USER_NAME>
```

### ✅ Create IAM Group
```bash
aws iam create-group \
  --group-name <IAM_GROUP_NAME>
```

### ✅ Add the User to the Group
```bash
aws iam add-user-to-group \
  --user-name <IAM_USER_NAME> \
  --group-name <IAM_GROUP_NAME>

```

## 🗑️ Delete User & Group

### ❌  Delete the IAM User
```bash
aws iam delete-user \
  --user-name <IAM_USER_NAME>
```

### ❌ Delete the IAM Group
```bash
aws iam delete-group \
  --group-name <IAM_GROUP_NAME>
```