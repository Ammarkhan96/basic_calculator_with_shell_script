This script is a simple shell-based calculator that performs basic arithmetic operations (addition, subtraction, multiplication, and division) between two numbers provided by the user. Here’s a breakdown of each part of the script:

Prompting for User Input:

echo "Enter first number: " and read num1: Asks the user to input the first number and stores it in the variable num1.
echo "Enter second number: " and read num2: Asks the user to input the second number and stores it in the variable num2.
echo "Choose an Operation (+, -, *, /):" and read op: Asks the user to choose an arithmetic operation (+, -, *, or /) and stores it in the variable op.
Performing the Chosen Operation:

case $op in ... esac: This case statement checks the value of op and matches it with one of the defined operations (+, -, *, /). Based on the user's choice, it performs the respective arithmetic operation using the bc command.

Addition (+):

result=$(echo "$num1 + $num2" | bc): This line calculates the sum of num1 and num2 using bc, a command-line calculator. The result is stored in the variable result.
echo "Result: $result": Prints the result of the addition.
Subtraction (-):

result=$(echo "$num1 - $num2" | bc): Calculates the difference between num1 and num2 and stores it in result.
echo "Result: $result": Prints the result of the subtraction.
Multiplication (*):

result=$(echo "$num1 * $num2" | bc): Calculates the product of num1 and num2 and stores it in result.
echo "Result: $result": Prints the result of the multiplication.
Division (/):

if [ "$num2" -eq 0 ]; then ... fi: This if statement checks if the second number (num2) is zero. Division by zero is undefined, so if num2 is zero, it prints an error message.
result=$(echo "scale=2; $num1 / $num2" | bc): If num2 is not zero, it performs the division with a precision of 2 decimal places (specified by scale=2 in bc) and stores the result in result.
echo "Result: $result": Prints the result of the division.
Handling Invalid Operations:

*): If the user enters an invalid operation (anything other than +, -, *, or /), this block executes.
echo "Invalid operation. Please use +, -, *, or /.": Prints an error message indicating that the user entered an invalid operation.
Explanation of Commands
read: Reads input from the user and stores it in a variable.
bc: A command-line calculator that can handle floating-point arithmetic.
case ... esac: A conditional statement that branches based on the value of a variable, similar to switch statements in other programming languages.
if ... fi: Conditional structure for handling division by zero.
