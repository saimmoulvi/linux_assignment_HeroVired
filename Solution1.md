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

## Output:

