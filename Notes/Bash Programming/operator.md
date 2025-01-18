### All operators
```bash
#!/bin/bash

# All-in-One Bash Operators Script

echo "=== Arithmetic Operators ==="
a=10
b=5

echo "Addition: $((a + b))"        # 10 + 5 = 15
echo "Subtraction: $((a - b))"     # 10 - 5 = 5
echo "Multiplication: $((a * b))"  # 10 * 5 = 50
echo "Division: $((a / b))"        # 10 / 5 = 2
echo "Modulus: $((a % b))"         # 10 % 5 = 0

echo
echo "=== Comparison Operators ==="
if [ $a -eq $b ]; then
  echo "$a is equal to $b"
else
  echo "$a is not equal to $b"
fi

if [ $a -gt $b ]; then
  echo "$a is greater than $b"
fi

if [ $a -lt $b ]; then
  echo "$a is less than $b"
fi

echo
echo "=== String Operators ==="
str1="hello"
str2="world"

if [ "$str1" == "$str2" ]; then
  echo "Strings are equal"
else
  echo "Strings are not equal"
fi

if [ -z "$str1" ]; then
  echo "String is empty"
else
  echo "String is not empty"
fi

if [ -n "$str1" ]; then
  echo "String has a non-zero length"
fi

echo
echo "=== Logical Operators ==="
if [ $a -gt 0 ] && [ $b -gt 0 ]; then
  echo "Both $a and $b are positive numbers"
fi

if [ $a -gt 0 ] || [ $b -lt 0 ]; then
  echo "Either $a is positive, or $b is negative"
fi

echo
echo "=== File Test Operators ==="
file="./example.txt"

if [ -e "$file" ]; then
  echo "File $file exists"
else
  echo "File $file does not exist"
fi

if [ -f "$file" ]; then
  echo "$file is a regular file"
fi

if [ -d "$file" ]; then
  echo "$file is a directory"
fi

if [ -r "$file" ]; then
  echo "$file is readable"
fi

if [ -w "$file" ]; then
  echo "$file is writable"
fi

if [ -x "$file" ]; then
  echo "$file is executable"
fi

echo
echo "=== Bitwise Operators ==="
bit1=5   # 0101
bit2=3   # 0011

echo "AND: $((bit1 & bit2))"        # 0101 & 0011 = 0001 = 1
echo "OR: $((bit1 | bit2))"         # 0101 | 0011 = 0111 = 7
echo "XOR: $((bit1 ^ bit2))"        # 0101 ^ 0011 = 0110 = 6
echo "Left Shift: $((bit1 << 1))"   # 0101 << 1 = 1010 = 10
echo "Right Shift: $((bit1 >> 1))"  # 0101 >> 1 = 0010 = 2

echo
echo "=== Special Operators ==="
# Substring
string="BashOperators"
echo "Substring: ${string:4:9}"     # Extracts 'Operators'

# Length
echo "Length of string: ${#string}"

# Command substitution
current_date=$(date)
echo "Current Date: $current_date"

echo
echo "=== End of Script ==="

```