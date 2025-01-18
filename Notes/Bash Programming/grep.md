```bash
#!/bin/bash

# Create an example file to work with
cat > example.txt <<EOF
Hello world
This is a test
Welcome to the grep tutorial
Another line with test
And one more test line
EOF

# Basic Search
echo "### Basic Search: Search for 'test'"
grep "test" example.txt
echo

# Case-Insensitive Search (-i)
echo "### Case-Insensitive Search: Search for 'hello' (ignoring case)"
grep -i "hello" example.txt
echo

# Count Matching Lines (-c)
echo "### Count Matching Lines: Count occurrences of 'test'"
grep -c "test" example.txt
echo

# Show Line Numbers (-n)
echo "### Show Line Numbers: Display line numbers for 'test'"
grep -n "test" example.txt
echo

# Match Whole Words Only (-w)
echo "### Match Whole Words Only: Search for 'test' as a whole word"
grep -w "test" example.txt
echo

# Show Non-Matching Lines (-v)
echo "### Show Non-Matching Lines: Lines not containing 'test'"
grep -v "test" example.txt
echo

# Recursive Search in Directories (-r)
echo "### Recursive Search: Search 'test' in all files under the current directory"
grep -r "test" .
echo

# Regular Expressions (-E for extended regex)
echo "### Regular Expressions: Search for 'test' or 'tutorial'"
grep -E "test|tutorial" example.txt
echo

# Show Matching Text in Color (--color)
echo "### Matching Text in Color: Highlight occurrences of 'test'"
grep --color "test" example.txt
echo

# Print Only Matching Part of Lines (-o)
echo "### Only Matching Part of Lines: Extract 'test'"
grep -o "test" example.txt
echo

# Search Multiple Patterns (-e)
echo "### Multiple Patterns: Search for 'test' or 'Hello'"
grep -e "test" -e "Hello" example.txt
echo

# Ignore Binary Files (--binary-files=text)
echo "### Ignore Binary Files: Avoid treating binary files differently"
grep --binary-files=text "test" example.txt
echo

```