## 2. File Backup:

Write a script that takes a directory as an argument and creates a backup of all `.txt` files in that directory. The backup files should be copied to a new directory named `backup` with a timestamp.

## Code:

```
#!/bin/bash

# Check if a directory was provided as an argument
if [ -z "$1" ]; then
  echo "Error: Please provide a directory as an argument"
  exit 1
fi

# Check if the provided directory exists
if [ ! -d "$1" ]; then
  echo "Error: Directory '$1' does not exist"
  exit 1
fi

# Create a timestamped backup directory
TIMESTAMP=$(date +"%Y-%m-%d_%H-%M-%S")
BACKUP_DIR="$1/backup_$TIMESTAMP"
mkdir -p "$BACKUP_DIR"

# Copy all .txt files to the backup directory
find "$1" -type f -name "*.txt" -exec cp {} "$BACKUP_DIR" \;

echo "Backup created in $BACKUP_DIR"
```

## Explanation:

- It checks if a directory was provided as an argument. If not, it exits with an error message..
- It checks if the provided directory exists. If not, it exits with an error message.
- It creates a timestamped backup directory inside the provided directory.
- It uses `find` to search for all `.txt` files in the provided directory and its subdirectories. For each file found, it uses `cp` to copy the file to the backup directory.
- Finally, it prints a success message indicating where the backup was created.

To execute the code save to the directory `linux_assignment` named `backup_files.sh`.   
Make the file executable with `chmod +x backup_files.sh`.  
Run the script with the destination directory as an argument like below

``
.backup_files.sh /path/to/directory
``

## Output:
![Screenshot 2024-08-24 145657](https://github.com/user-attachments/assets/e33158f0-a43b-4b82-aff5-1ff7555ad9e2)
