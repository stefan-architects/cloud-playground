## ✨ Placeholder Reference

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<BUCKET_NAME>`                           | Globally unique S3 bucket name                                              |
| `<REGION>`                                | AWS region where the bucket will be created                                 |
| `<VERSIONING_CONFIGURATION>`              | Value for --versioning-configuration (Status=Enabled or Status=Suspended)   |       
| `<PUBLIC_ACCESS_BLOCK_CONFIGURATION>` | Public access block settings (e.g., BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true) |
| `<ENCRYPTION_CONFIGURATION>` | SSE-S3 encryption rule (e.g., '{"Rules":[{"ApplyServerSideEncryptionByDefault":{"SSEAlgorithm":"AES256"}}]}') |

📌 **Replace all placeholder values with your own values before running the commands.**

----

## 🏗️ Bucket Configuration

### 🧰 Create the bucket
```bash
aws s3api create-bucket \
  --bucket <BUCKET_NAME> \
  --region <REGION>
```

### 🧰 Enable versioning
```bash
aws s3api put-bucket-versioning \
  --bucket <BUCKET_NAME> \
  --versioning-configuration Status=Enabled
```

### 🧰 Block all public access
```bash
aws s3api put-public-access-block \
  --bucket <BUCKET_NAME> \
  --public-access-block-configuration \
      BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true
```

### 🧰 Enable default encryption (SSE-S3)
```bash
aws s3api put-bucket-encryption \
  --bucket <BUCKET_NAME> \
  --server-side-encryption-configuration \
      '{"Rules":[{"ApplyServerSideEncryptionByDefault":{"SSEAlgorithm":"AES256"}}]}'
```

----

### 💥 Bucket Deletion
```bash
aws s3api delete-bucket \
  --bucket <BUCKET_NAME> \
  --region <REGION>
```