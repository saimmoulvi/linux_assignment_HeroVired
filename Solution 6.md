## 6) Automated Backup:
Write a script that compresses the `/home/user/documents` directory into a tarball named `documents_backup.tar.gz` and moves it to the `/home/user/backup` directory. This script should be scheduled to run daily using cron.

## Code:
```
#!/bin/bash

# Set source and destination directories
SOURCE_DIR="/home/user/documents"
DESTINATION_DIR="/home/user/backup"

# Set tarball name
TARBALL_NAME="documents_backup.tar.gz"

# Compress source directory into tarball
tar -czf "$TARBALL_NAME" "$SOURCE_DIR"

# Move tarball to destination directory
mv "$TARBALL_NAME" "$DESTINATION_DIR"
echo "Backup Successfull"
```

Setting up crontab to run the script daily at midnight

`crontab -e`   
`0 0 * * * /home/saimmoulvi/backup_doc.sh`
