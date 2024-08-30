## 5. File Permission Checker:   
Write a script that takes a file as an argument and checks if the file has read, write, and execute permissions. The script should display appropriate messages for each permission.

## Code:

```
#!/bin/bash

# Check if a file argument is provided
if [ $# -eq 0 ]; then
  echo "Please provide a file as an argument"
  exit 1
fi

# Get the file argument
FILE=$1

# Check if the file exists
if [ ! -f "$FILE" ]; then
  echo "File $FILE does not exist"
  exit 1
fi

# Check permissions
if [ -r "$FILE" ]; then
  echo "File $FILE has read permission"
else
  echo "File $FILE does not have read permission"
fi

if [ -w "$FILE" ]; then
  echo "File $FILE has write permission"
else
  echo "File $FILE does not have write permission"
fi

if [ -x "$FILE" ]; then
  echo "File $FILE has execute permission"
else
  echo "File $FILE does not have execute permission"
fi
```

# Explanation:
- `if [ $# -eq 0 ]; then`: This line checks if a file argument is provided. If not, it displays an error message and exits.
- `FILE=$1`: This line gets the file argument passed to the script.
- `if [ ! -f "$FILE" ]; then`: This line checks if the file exists. If not, it displays an error message and exits.
- The three `if` statements check for read, write, and execute permissions using the `-r`, `-w`, and `-x` options, respectively. If the permission is present, it displays a
  message indicating that the file has the permission. Otherwise, it displays a message indicating that the file does not have the permission.
  
To execute the code save to the directory linux_assignment named file_permission.sh.    
Make the file executable with chmod +x file_permission.   
Run the script with the following command `./file_permission.sh`

## Output: 

![5](https://github.com/user-attachments/assets/fccfea40-9e75-482a-b085-0f4b40a9c795)




