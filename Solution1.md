## 1. Create a Directory Structure:

Write a script that creates the following directory structure:

   /home/user/

       ├── projects/

       │   ├── project1/

       │   ├── project2/

       │   └── project3/

       ├── documents/

       └── downloads/
       
## Code:

```

#!/bin/bash

# Create the main directory
mkdir -p /home/user

mkdir -p /home/user/projects
mkdir -p /home/user/projects/project1
mkdir -p /home/user/projects/project2
mkdir -p /home/user/projects/project3

mkdir -p /home/user/documents
mkdir -p /home/user/downloads

echo "Directory structure created successfully."
```

The -p option is used to create the directory with parents, meaning that if the parent directory does not exist, it will be created as well.

## Output:
![Screenshot 2024-08-18 181800](https://github.com/user-attachments/assets/ea2de512-ec85-4736-92a8-df6c8d2a093d)
