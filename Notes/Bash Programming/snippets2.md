### User input
```bash 
#!/bin/bash

# 1. Basic Input
read -p "Enter your name: " name
echo "Hello, $name!"

# 2. Input with Default Value
read -p "Enter your age (default is 18): " age
age=${age:-18}
echo "Your age is $age."

# 3. Password Input
read -sp "Enter your password: " password
echo -e "\nYour password is saved."

# 4. Input Validation
while true; do
  read -p "Enter a number between 1 and 10: " num
  if [[ $num -ge 1 && $num -le 10 ]]; then
    echo "Valid input: $num"
    break
  else
    echo "Invalid input. Please try again."
  fi
done

# 5. Multiple Inputs
read -p "Enter your first and last name: " first last
echo "First Name: $first, Last Name: $last"

# 6. Input with Timeout
read -t 10 -p "Enter your favorite color (timeout in 10 seconds): " color
if [ -z "$color" ]; then
  echo "No input provided within the timeout."
else
  echo "Your favorite color is $color."
fi

# 7. Reading Input in a Loop
echo "Enter numbers one by one (type 'q' to quit):"
while true; do
  read -p "Number: " num
  if [ "$num" == "q" ]; then
    echo "Exiting the loop."
    break
  fi
  echo "You entered: $num"
done

# 8. Reading Input from File
file="input.txt"
if [ -f "$file" ]; then
  while IFS= read -r line; do
    echo "Line: $line"
  done < "$file"
else
  echo "File not found: $file"
fi

# 9. Input with Confirmation
read -p "Are you sure you want to continue? (yes/no): " confirm
if [[ "$confirm" =~ ^[Yy]([Ee][Ss])?$ ]]; then
  echo "You chose to continue."
else
  echo "Operation canceled."
fi

# 10. Reading Array Input
echo "Enter array elements separated by space: "
read -a array
echo "Array elements are: "
for element in "${array[@]}"; do
  echo "$element"
done

# 11. Reading File Names into an Array
read -p "Enter file names separated by space: " -a files
echo "You entered the following files: "
for file in "${files[@]}"; do
  if [ -f "$file" ]; then
    echo "$file exists."
  else
    echo "$file does not exist."
  fi
done


```

```bash
#!/bin/bash

# Integer Specifiers
echo "---- Integer Specifiers ----"
printf "Decimal: %d\n" 42                   # Output: Decimal: 42
printf "Hexadecimal (lowercase): %x\n" 255  # Output: Hexadecimal (lowercase): ff
printf "Hexadecimal (uppercase): %X\n" 255  # Output: Hexadecimal (uppercase): FF
printf "Octal: %o\n" 255                    # Output: Octal: 377
printf "Unsigned decimal: %u\n" 42          # Output: Unsigned decimal: 42

# Floating-Point Specifiers
echo "---- Floating-Point Specifiers ----"
printf "Fixed-point: %.2f\n" 3.14159         # Output: Fixed-point: 3.14
printf "Scientific notation: %.2e\n" 3.14159 # Output: Scientific notation: 3.14e+00
printf "General format: %.2g\n" 3.14159      # Output: General format: 3.1

# String Specifiers
echo "---- String Specifiers ----"
printf "String: %s\n" "Hello, World!"       # Output: String: Hello, World!
printf "Quoted String: %q\n" "Hello, World!" # Output: Quoted String: 'Hello, World!'

# Character Specifiers
echo "---- Character Specifiers ----"
printf "Character: %c\n" 65                  # Output: Character: A (ASCII value for 'A')

# Padding and Width
echo "---- Padding and Width Specifiers ----"
printf "Width: '%10s'\n" "Hello"             # Output: Width: '     Hello'
printf "Left-aligned: '%-10s'\n" "Hello"     # Output: Left-aligned: 'Hello     '
printf "Zero-padded: '%010d'\n" 42           # Output: Zero-padded: 0000000042

# Special Characters
echo "---- Special Characters ----"
printf "Newline: %b\n" "Line 1\nLine 2"      # Output: Newline: Line 1
                                            #         Line 2
printf "Tab: %b\n" "Hello\tWorld"            # Output: Tab: Hello    World
printf "Backslash: %b\n" "Path\\To\\File"    # Output: Backslash: Path\To\File

# Multiple Format Specifiers in One
echo "---- Multiple Format Specifiers ----"
printf "String: %s, Integer: %d, Float: %.2f\n" "Test" 42 3.14159 
# Output: String: Test, Integer: 42, Float: 3.14

```

