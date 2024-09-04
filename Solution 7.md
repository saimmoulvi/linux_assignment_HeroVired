## 7) Process Monitor:
Write a script that checks if a specific process (e.g., `apache2`) is running. If the process is not running, the script should start the process and log the action to a file.

## Code:

```
#!/bin/bash

# Set process name
PROCESS_NAME="apache2"

# Set log file
LOG_FILE="/var/log/process_monitor.log"

# Check if process is running
if pgrep -f "$PROCESS_NAME" > /dev/null
then
  echo "[$(date)] $PROCESS_NAME is running." >> "$LOG_FILE"
else
  # Start process
  service "$PROCESS_NAME" start
  echo "[$(date)] $PROCESS_NAME was not running, started successfully." >> "$LOG_FILE"
fi
```
