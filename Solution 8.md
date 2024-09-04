## 8)  Text File Analysis:
Write a script that takes a text file as an argument and counts the number of lines, words, and characters in the file. The script should display the counts.

```
#!/bin/bash

# Check if file argument is provided
if [ $# -eq 0 ]; then
  echo "Please provide a file as an argument."
  exit 1
fi

# Set file path
FILE_PATH="$1"

# Check if file exists
if [ ! -f "$FILE_PATH" ]; then
  echo "File not found: $FILE_PATH"
  exit 1
fi

# Count lines, words, and characters
LINE_COUNT=$(wc -l < "$FILE_PATH")
WORD_COUNT=$(wc -w < "$FILE_PATH")
CHAR_COUNT=$(wc -m < "$FILE_PATH")

# Display counts
echo "File: $FILE_PATH"
echo "Lines: $LINE_COUNT"
echo "Words: $WORD_COUNT"
echo "Characters: $CHAR_COUNT"
```

## Output:

![Solution8](https://github.com/user-attachments/assets/9a54761a-b3ea-4710-beab-6301f5034119)
