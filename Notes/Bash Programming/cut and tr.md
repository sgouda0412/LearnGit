```bash
#!/bin/bash

# Create an example file to work with
cat > example.txt <<EOF
ID,Name,Age,Location
1,John,25,New York
2,Sarah,30,Los Angeles
3,Michael,35,Chicago
4,Emily,40,Houston
EOF

echo "### Input File (example.txt)"
cat example.txt
echo

########################################
# Examples for `cut`
########################################

# Extract specific fields (columns) from a file using a delimiter (-d)
echo "### Extract the 'Name' and 'Age' columns (2nd and 3rd fields)"
cut -d ',' -f 2,3 example.txt
echo

# Extract characters by position (-c)
echo "### Extract characters 1-3 from each line"
cut -c 1-3 example.txt
echo

# Extract from a specific byte position onwards (-b)
echo "### Extract bytes 5 and onward (useful for fixed-width files)"
cut -b 5- example.txt
echo

# Suppress lines without delimiters (--complement)
echo "### Complement example: Remove the first column"
cut -d ',' --complement -f 1 example.txt
echo

########################################
# Examples for `tr`
########################################

# Translate characters (replace characters)
echo "### Replace all commas with tabs"
cat example.txt | tr ',' '\t'
echo

# Convert lowercase to uppercase
echo "### Convert all lowercase letters to uppercase"
cat example.txt | tr 'a-z' 'A-Z'
echo

# Delete specific characters (-d)
echo "### Remove all commas"
cat example.txt | tr -d ','
echo

# Squeeze repeated characters (-s)
echo "### Squeeze multiple spaces into a single space"
echo "Hello     World!   Welcome   to   tr!" | tr -s ' '
echo

# Combine translation and deletion
echo "### Remove all digits and convert to uppercase"
echo "abc123def456ghi789" | tr -d '0-9' | tr 'a-z' 'A-Z'
echo

# Limit output to specific character ranges
echo "### Remove all non-alphanumeric characters"
echo "Hello!@#123World$%^456" | tr -cd 'a-zA-Z0-9'
echo

########################################
# Combining `cut` and `tr`
########################################

echo "### Combine cut and tr: Extract 'Name' column and replace lowercase with uppercase"
cut -d ',' -f 2 example.txt | tr 'a-z' 'A-Z'
echo


```

---

```bash
#!/bin/bash

# Create an example file to work with
cat > example.txt <<EOF
ID,Name,Age,Location
1,John,25,New York
2,Sarah,30,Los Angeles
3,Michael,35,Chicago
4,Emily,40,Houston
EOF

echo "### Input File (example.txt)"
cat example.txt
echo

########################################
# `cut` Command Examples
########################################

# 1. Extract specific fields using a delimiter (-d and -f)
echo "### 1. Extract 'Name' and 'Age' columns (fields 2 and 3)"
cut -d ',' -f 2,3 example.txt
echo

# 2. Extract only the first field
echo "### 2. Extract the 'ID' column (field 1)"
cut -d ',' -f 1 example.txt
echo

# 3. Extract characters by position (-c)
echo "### 3. Extract characters 1-5 from each line"
cut -c 1-5 example.txt
echo

# 4. Extract characters starting from a specific position
echo "### 4. Extract characters from position 5 onwards"
cut -c 5- example.txt
echo

# 5. Extract bytes using fixed-width columns (-b)
echo "### 5. Extract bytes 1-4 (for fixed-width files)"
cut -b 1-4 example.txt
echo

# 6. Remove specific fields with complement (--complement)
echo "### 6. Remove 'ID' column (field 1)"
cut -d ',' --complement -f 1 example.txt
echo

# 7. Extract fields with a custom delimiter (e.g., pipe `|`)
echo "### 7. Extract fields using a custom delimiter (pipe)"
echo "1|John|25|New York" | cut -d '|' -f 2,4
echo

# 8. Extract last N fields using tail-like syntax
echo "### 8. Extract the last 2 fields"
cut -d ',' -f 3- example.txt
echo

# 9. Combine multiple `cut` commands
echo "### 9. Extract 'Name' field and truncate to 3 characters"
cut -d ',' -f 2 example.txt | cut -c 1-3
echo

# 10. Use `cut` to extract fields from command output
echo "### 10. Extract file permissions from 'ls -l'"
ls -l | cut -c 1-10
echo

########################################
# `tr` Command Examples
########################################

# 11. Replace all commas with tabs
echo "### 11. Replace commas with tabs"
cat example.txt | tr ',' '\t'
echo

# 12. Convert all lowercase to uppercase
echo "### 12. Convert lowercase letters to uppercase"
cat example.txt | tr 'a-z' 'A-Z'
echo

# 13. Convert all uppercase to lowercase
echo "### 13. Convert uppercase letters to lowercase"
echo "HELLO WORLD" | tr 'A-Z' 'a-z'
echo

# 14. Delete specific characters
echo "### 14. Remove all commas"
cat example.txt | tr -d ','
echo

# 15. Squeeze repeated spaces into a single space
echo "### 15. Squeeze multiple spaces into one space"
echo "Hello     World!   Welcome    to   tr!" | tr -s ' '
echo

# 16. Replace digits with a specific character
echo "### 16. Replace digits with 'X'"
echo "ID123Name456" | tr '0-9' 'X'
echo

# 17. Delete non-alphanumeric characters
echo "### 17. Remove all non-alphanumeric characters"
echo "Hello!@#123World$%^456" | tr -cd 'a-zA-Z0-9'
echo

# 18. Translate one set of characters to another
echo "### 18. Replace 'aeiou' with '12345'"
echo "Hello World" | tr 'aeiou' '12345'
echo

# 19. Replace and delete combined
echo "### 19. Remove digits and convert letters to uppercase"
echo "abc123def456ghi789" | tr -d '0-9' | tr 'a-z' 'A-Z'
echo

# 20. Squeeze and replace spaces
echo "### 20. Replace spaces with underscores and squeeze multiple spaces"
echo "Hello     World!   Welcome    to   tr!" | tr -s ' ' | tr ' ' '_'
echo

```
