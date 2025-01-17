### echo
---
```bash
#!/bin/bash  # Shebang
echo -E "Line 1\nLine 2" # No special handling for new line character 
echo -e "Line 1\nLine 2\tIndented"  # Use escape sequence
echo -n "Processing..."  #Suppress new line
read -p "Enter your name: " name  # Display prompt and read input from a user in a single line
```

### read
---
```bash

-p -> Display a prompt before waiting for input.-> 
read -p "Enter your name: " name

-s|Silent mode. Input is not displayed on the screen (useful for passwords)-> 
read -s -p "Enter your password: " password

-t Timeout. Waits for input for a specified number of seconds.
read -t 5 -p "Enter your name within 5 seconds: " name

-n|Reads only a specified number of characters.|
read -n 1 -p "Press any key to continue..."

-d|Use a specific delimiter to end input (default is newline).
read -d ";" -p "Enter a list separated by semicolon: " input

-r|Disables backslash escape interpretation (reads raw input).
read -r -p "Enter raw text (e.g., with backslashes): " input

-a Reads input into an array (split by IFS).|
read -a arr -p "Enter space-separated values: "

-e Enables command-line editing (uses Readline for input editing).
read -e -p "Enter a command: " cmd

-u  Reads input from a file descriptor (useful for advanced scripting.         exec 3<file.txt; read -u 3 line
```

### FOR LOOPS
```bash
#!/bin/bash

# 1. Basic for Loop
for color in red green blue; do
  echo "Color: $color"
done

# 2. C-Style for Loop
for ((i = 1; i <= 5; i++)); do
  echo "Number: $i"
done

# 3. For Loop Over a Range
# Example 1: Simple Range
for num in {1..5}; do
  echo "Number: $num"
done

# Example 2: Range with Step
for num in {1..10..2}; do
  echo "Number: $num"
done

# 4. Iterating Over Files or Command Output
# Example 1: Files in a Directory
for file in /path/to/directory/*; do
  echo "File: $file"
done

# Example 2: Command Output
for user in $(cat /etc/passwd | cut -d: -f1); do
  echo "User: $user"
done

# 5. For Loop with Array
arr=("apple" "banana" "cherry")
for fruit in "${arr[@]}"; do
  echo "Fruit: $fruit"
done

# 6. For Loop with Break
for i in {1..10}; do
  if [ "$i" -eq 5 ]; then
    echo "Breaking at $i"
    break
  fi
  echo "Number: $i"
done

# 7. For Loop with Continue
for i in {1..5}; do
  if [ "$i" -eq 3 ]; then
    echo "Skipping $i"
    continue
  fi
  echo "Number: $i"
done

# 8. Infinite For Loop
# Uncomment to test (use Ctrl+C to stop)
# for (( ; ; )); do
#   echo "This will run forever."
#   sleep 1
# done

# 9. Nested For Loops
for i in {1..3}; do
  for j in {a..c}; do
    echo "Combination: $i$j"
  done
done

# 10. For Loop with Commands in a Subshell
for dir in /path/to/*; do
  (cd "$dir" && echo "Inside directory: $(pwd)")
done

```

> 
### While Loops
```bash 
#!/bin/bash

# 1. Basic While Loop
count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++))
done

# 2. While Loop with Condition
number=10
while [ $number -gt 0 ]; do
  echo "Number: $number"
  ((number--))
done

# 3. Infinite While Loop
# Uncomment to test (use Ctrl+C to stop)
# while true; do
#   echo "This will run forever."
#   sleep 1
# done

# 4. Reading a File Line by Line
file="example.txt"
if [ -f "$file" ]; then
  while IFS= read -r line; do
    echo "Line: $line"
  done < "$file"
else
  echo "File not found: $file"
fi

# 5. While Loop with Break
num=1
while [ $num -le 10 ]; do
  if [ $num -eq 5 ]; then
    echo "Breaking at $num"
    break
  fi
  echo "Number: $num"
  ((num++))
done

# 6. While Loop with Continue
num=1
while [ $num -le 5 ]; do
  if [ $num -eq 3 ]; then
    echo "Skipping $num"
    ((num++))
    continue
  fi
  echo "Number: $num"
  ((num++))
done

# 7. Nested While Loops
outer=1
while [ $outer -le 3 ]; do
  inner=1
  while [ $inner -le 2 ]; do
    echo "Outer: $outer, Inner: $inner"
    ((inner++))
  done
  ((outer++))
done

# 8. While Loop with Arithmetic Expression
counter=1
while ((counter <= 5)); do
  echo "Counter: $counter"
  ((counter++))
done

# 9. While Loop Over Command Output
while read -r user; do
  echo "User: $user"
done < <(cut -d: -f1 /etc/passwd)

```
### Until loops
```bash 
#!/bin/bash

# 1. Basic Until Loop
count=1
until [ $count -gt 5 ]; do
  echo "Count: $count"
  ((count++))
done

# 2. Until Loop with Condition
number=10
until [ $number -le 0 ]; do
  echo "Number: $number"
  ((number--))
done

# 3. Infinite Until Loop
# Uncomment to test (use Ctrl+C to stop)
# until false; do
#   echo "This will run forever."
#   sleep 1
# done

# 4. Reading a File Line by Line with Until
file="example.txt"
if [ -f "$file" ]; then
  until ! IFS= read -r line; do
    echo "Line: $line"
  done < "$file"
else
  echo "File not found: $file"
fi

# 5. Until Loop with Break
num=1
until [ $num -gt 10 ]; do
  if [ $num -eq 5 ]; then
    echo "Breaking at $num"
    break
  fi
  echo "Number: $num"
  ((num++))
done

# 6. Until Loop with Continue
num=1
until [ $num -gt 5 ]; do
  if [ $num -eq 3 ]; then
    echo "Skipping $num"
    ((num++))
    continue
  fi
  echo "Number: $num"
  ((num++))
done

# 7. Nested Until Loops
outer=1
until [ $outer -gt 3 ]; do
  inner=1
  until [ $inner -gt 2 ]; do
    echo "Outer: $outer, Inner: $inner"
    ((inner++))
  done
  ((outer++))
done

# 8. Until Loop with Arithmetic Expression
counter=1
until ((counter > 5)); do
  echo "Counter: $counter"
  ((counter++))
done

# 9. Until Loop Over Command Output
until ! read -r user; do
  echo "User: $user"
done < <(cut -d: -f1 /etc/passwd)

```

### Conditional Statements
```bash 
#!/bin/bash

# 1. If-Else Conditional Statement
num=10
if [ $num -gt 5 ]; then
  echo "$num is greater than 5"
else
  echo "$num is not greater than 5"
fi

# 2. If-ElseIf-Else Statement
if [ $num -lt 5 ]; then
  echo "$num is less than 5"
elif [ $num -eq 10 ]; then
  echo "$num is equal to 10"
else
  echo "$num is greater than 5 but not equal to 10"
fi

# 3. Nested If Statements
if [ $num -ge 5 ]; then
  if [ $num -le 15 ]; then
    echo "$num is between 5 and 15"
  fi
fi

# 4. Case Statement
fruit="apple"
case $fruit in
  "apple")
    echo "You chose apple."
    ;;
  "banana")
    echo "You chose banana."
    ;;
  "cherry")
    echo "You chose cherry."
    ;;
  *)
    echo "Unknown fruit."
    ;;
esac

# 5. Logical AND
if [ $num -gt 5 ] && [ $num -lt 20 ]; then
  echo "$num is greater than 5 AND less than 20"
fi

# 6. Logical OR
if [ $num -lt 5 ] || [ $num -gt 15 ]; then
  echo "$num is less than 5 OR greater than 15"
fi

# 7. String Comparison
str="hello"
if [ "$str" == "hello" ]; then
  echo "The string is 'hello'"
fi

# 8. File Conditions
file="example.txt"
if [ -f "$file" ]; then
  echo "File exists."
else
  echo "File does not exist."
fi

# 9. Combining Conditions with Parentheses
if [[ $num -gt 5 && ( $num -lt 20 || $num -eq 25 ) ]]; then
  echo "$num satisfies the combined conditions"
fi

```

