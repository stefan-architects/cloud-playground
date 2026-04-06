
## ✨ Placeholder Reference
Replace the placeholder values with your own values

| Placeholder       | Description                                                   |
|-------------------|---------------------------------------------------------------|
| `<DB_INSTANCE_CLASS>` | The RDS instance class, e.g., `db.t4g.micro` |
| `<DB_INSTANCE_IDENTIFIER>` | Unique name for the database instance |
| `<MASTER_USERNAME>` | Admin username for the DB |
| `<MASTER_PASSWORD>` | Admin password for the DB |
| `<ALLOCATED_STORAGE_GB>` | Storage size in gigabytes |
| `<STORAGE_TYPE>` | Storage type such as `gp2`, `gp3`, or `io1` |
| `<BACKUP_RETENTION_DAYS>` | Number of days to retain backups (`0` disables backups) |
| `<MULTI_AZ_FLAG>` | Either `--multi-az` or `--no-multi-az` |

### Create Table
```bash
aws rds create-db-instance \
  --engine mysql \
  --db-instance-class <DB_INSTANCE_CLASS> \
  --db-instance-identifier <DB_INSTANCE_IDENTIFIER> \
  --master-username <MASTER_USERNAME> \
  --master-user-password <MASTER_PASSWORD> \
  --allocated-storage <ALLOCATED_STORAGE_GB> \
  --storage-type <STORAGE_TYPE> \
  --backup-retention-period <BACKUP_RETENTION_DAYS> \
  <MULTI_AZ_FLAG>
```

### Delete Table
| Placeholder | Meaning |
|------------|---------|
| `<DB_INSTANCE_IDENTIFIER>` | The unique name of the DB instance you want to delete |
| `<FINAL_SNAPSHOT_FLAG>` | Either `--skip-final-snapshot` or `--final-db-snapshot-identifier <SNAPSHOT_NAME>` |


```bash
aws rds delete-db-instance \
  --db-instance-identifier still-dont-have-a-name \
  --skip-final-snapshot
```