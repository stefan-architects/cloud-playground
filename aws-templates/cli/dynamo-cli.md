## ✨ Placeholder Reference
Replace the placeholder values with your own values

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<DDB_TABLE_NAME>` | Name of the DynamoDB table to create or delete |
| `<PRIMARY_KEY_NAME>` | The name of the table's primary (hash) key |
| `<PRIMARY_KEY_TYPE>` | The key type: `S` (string), `N` (number), or `B` (binary) |
| `<READ_CAPACITY>` | Provisioned read capacity units (for provisioned mode) |
| `<WRITE_CAPACITY>` | Provisioned write capacity units (for provisioned mode) |

### 🧰 Create DynamoDB Table
```bash
aws dynamodb create-table \
  --table-name <DDB_TABLE_NAME> \
  --attribute-definitions AttributeName=<PRIMARY_KEY_NAME>,AttributeType=<PRIMARY_KEY_TYPE> \
  --key-schema AttributeName=<PRIMARY_KEY_NAME>,KeyType=HASH \
  --provisioned-throughput ReadCapacityUnits=<READ_CAPACITY>,WriteCapacityUnits=<WRITE_CAPACITY>
```

----

### 💥 Delete DynamoDB Table
```bash
aws dynamodb delete-table \
  --table-name <DDB_TABLE_NAME>
```