## 3. User Information:
   Write a script that displays the following information about the user:

   - Username

   - User ID

   - Group ID

   - Home Directory

   - Shell being used

 ## Code:

```
#!/bin/bash

# Get the username
USERNAME=$(whoami)

# Get the user ID
USER_ID=$(id -u)

# Get the group ID
GROUP_ID=$(id -g)

# Get the home directory
HOME_DIR=$(echo ~)

# Get the shell being used
SHELL=$(echo $SHELL)

# Display the information
echo "Username: $USERNAME"
echo "User ID: $USER_ID"
echo "Group ID: $GROUP_ID"
echo "Home Directory: $HOME_DIR"
echo "Shell: $SHELL"
```

## Explanation: 
- `USERNAME=$(whoami)`: This line uses the `whoami` command to get the current username and stores it in the `USERNAME` variable.
- `USER_ID=$(id -u`): This line uses the `id` command with the `-u` option to get the user ID and stores it in the `USER_ID` variable.
- `GROUP_ID=$(id -g)`: This line uses the `id` command with the `-g` option to get the group ID and stores it in the `GROUP_ID` variable.
- `HOME_DIR=$(echo ~)`: This line uses the `echo` command with the `~` symbol to get the home directory and stores it in the `HOME_DIR` variable. The `~` symbol is a shortcut for the home directory.
- `SHELL=$(echo $SHELL)`: This line uses the `echo` command to get the value of the `SHELL` environment variable, which stores the path to the shell being used.
- The last five lines display the information using `echo` statements.

To execute the code save to the directory linux_assignment named user_info.sh.  
Make the file executable with `chmod +x user_info.sh`.  
Run the script with the following command below  

`./user_info.sh`  

## Output:

![Solution3](https://github.com/user-attachments/assets/4b7f7afb-1e62-4f8d-9849-868500457493)


  

