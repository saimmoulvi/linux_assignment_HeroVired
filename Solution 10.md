## 10) Simple Calculator:
Write a script that acts as a simple calculator. The script should prompt the user to enter two numbers and an operator (+, -, *, /) and then display the result of the operation

##Code:

```
#!/bin/bash

# Prompt user for numbers and operator
echo "Simple Calculator"
echo "-----------------"
read -p "Enter the first number: " num1
read -p "Enter the second number: " num2
read -p "Enter the operator (+, -, *, /): " operator

# Perform operation based on operator
case $operator in
  "+")
    result=$(echo "$num1 + $num2" | bc)
    ;;
  "-")
    result=$(echo "$num1 - $num2" | bc)
    ;;
  "*")
    result=$(echo "$num1 * $num2" | bc)
    ;;
  "/")
    if [ $num2 -eq 0 ]; then
      echo "Error: Division by zero is not allowed."
      exit 1
    fi
    result=$(echo "$num1 / $num2" | bc)
    ;;
  *)
    echo "Error: Invalid operator. Please enter +, -, *, or /."
    exit 1
    ;;
esac

# Display result
echo "Result: $result"

echo "Calculation complete. Thank you for using the simple calculator!"

```
Before running the script, kindly install Basic Calculator (bc) using the following command   
`sudo apt install bc`

## Output:
![Solution10](https://github.com/user-attachments/assets/dac13ab5-3b10-4130-96ab-53d6f4c01701)

