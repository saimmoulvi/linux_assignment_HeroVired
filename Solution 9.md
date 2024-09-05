## 9) System Information Report:
Write a script that generates a system information report. The report should include:

   - System uptime

   - Memory usage

   - CPU load

   - Disk usage

   - Running processes

The report should be saved to a file named `system_report.txt`.

## Code:

```
#!/bin/bash

# Set report file
REPORT_FILE="system_report.txt"

# Clear previous report
> "$REPORT_FILE"

# System uptime
UPTIME=$(uptime -p)
echo "System Uptime: $UPTIME" >> "$REPORT_FILE"

# Memory usage
MEMORY_USAGE=$(free -h --si)
echo "Memory Usage:" >> "$REPORT_FILE"
echo "$MEMORY_USAGE" >> "$REPORT_FILE"

# CPU load
CPU_LOAD=$(mpstat -a | awk '$12 ~ /[0-9.]+/ { print 100 - $12 "%"}')
echo "CPU Load: $CPU_LOAD" >> "$REPORT_FILE"

# Disk usage
DISK_USAGE=$(df -h --si)
echo "Disk Usage:" >> "$REPORT_FILE"
echo "$DISK_USAGE" >> "$REPORT_FILE"

# Running processes
RUNNING_PROCESSES=$(ps -ef | wc -l)
echo "Running Processes: $RUNNING_PROCESSES" >> "$REPORT_FILE"

# List of running processes
echo "List of Running Processes:" >> "$REPORT_FILE"
ps -ef >> "$REPORT_FILE"

echo "" >> "$REPORT_FILE"
echo "Report generated on: $(date)" >> "$REPORT_FILE"
echo "System report generated successfully. Check $REPORT_FILE for details."

```
