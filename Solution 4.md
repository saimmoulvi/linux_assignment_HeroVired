## 4. Disk Usage Alert:  
Write a script that takes a file as an argument and checks if the file has read, write, and execute permissions. The script should display appropriate messages for each permission.

## Code:
```
#!/bin/bash

# Set the threshold for disk usage (80% in this case)
THRESHOLD=80

# Get the current disk usage of the root filesystem
USAGE=$(df -h / | awk '{print $5}' | sed 's/%//')

# Check if the disk usage is above the threshold
if [ $USAGE -gt $THRESHOLD ]; then
  # Send an email alert to the system administrator
  SUBJECT="Disk usage alert: Root filesystem usage is $USAGE%"
  BODY="The root filesystem usage has exceeded $THRESHOLD%. Current usage is $USAGE%."
  echo "$BODY" | mail -s "$SUBJECT" admin@example.com
fi
```

## Explanation:

- The first line sets the threshold for disk usage to 80%.
- The second line uses the `df` command to get the current disk usage of the root filesystem.
- The `-h` option tells `df` to display the output in a human-readable format.
- The `awk` command extracts the fifth column (which contains the usage percentage),
- The `sed` command removes the `%` symbol from the output.
- The third line checks if the disk usage is above the threshold using a simple comparison.
- If the disk usage is above the threshold, the script sends an email alert to the system administrator using the `mail` command.
- The email subject and body are constructed using the `SUBJECT` and `BODY` variables, respectively.

To execute the code save to the directory linux_assignment named disk_usage.sh.  
Make the file executable with chmod +x disk_usage.sh  
Run the script with the following command `./disk_usage.sh`
  
