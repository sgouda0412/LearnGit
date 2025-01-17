```bash
#!/bin/bash

# Create and Write to a File
echo "---- Create and Write to a File ----"
echo "Hello, World!" > hello.txt          # Write a line to hello.txt
echo "This is a test." >> hello.txt       # Append to hello.txt
printf "Writing formatted text: %s\n" "Formatted Line" >> hello.txt # Write formatted text

# Reading from a File
echo "---- Reading from a File ----"
echo "File content:"
cat hello.txt                            # Output the content of hello.txt
echo ""

# Read file line by line
echo "Reading file line by line:"
while IFS= read -r line; do
    echo "$line"
done < hello.txt

# File Information
echo "---- File Information ----"
echo "File Size:"
stat -c %s hello.txt                     # Output file size in bytes
echo "File Type:"
file hello.txt                            # Output file type
echo "File Permissions:"
ls -l hello.txt                          # Output file permissions

# File Existence Check
echo "---- File Existence Check ----"
if [ -f "hello.txt" ]; then
    echo "hello.txt exists."
else
    echo "hello.txt does not exist."
fi

# Check if file is readable
if [ -r "hello.txt" ]; then
    echo "hello.txt is readable."
else
    echo "hello.txt is not readable."
fi

# Check if file is writable
if [ -w "hello.txt" ]; then
    echo "hello.txt is writable."
else
    echo "hello.txt is not writable."
fi

# Renaming a File
echo "---- Renaming a File ----"
mv hello.txt renamed_hello.txt           # Rename hello.txt to renamed_hello.txt
echo "File renamed to renamed_hello.txt."

# Moving a File
echo "---- Moving a File ----"
mkdir -p moved_files                     # Create directory for moving files
mv renamed_hello.txt moved_files/         # Move the file to the new directory
echo "File moved to 'moved_files/'."

# Copying a File
echo "---- Copying a File ----"
cp moved_files/renamed_hello.txt moved_files/copy_of_hello.txt  # Copy the file
echo "File copied to 'moved_files/copy_of_hello.txt'."

# Deleting a File
echo "---- Deleting a File ----"
rm moved_files/copy_of_hello.txt         # Delete the copied file
echo "File 'copy_of_hello.txt' deleted."

# Creating a Directory
echo "---- Creating a Directory ----"
mkdir new_directory                      # Create a new directory
echo "Directory 'new_directory' created."

# Listing Files in a Directory
echo "---- Listing Files in a Directory ----"
echo "Files in the current directory:"
ls -l                                    # List all files in the current directory

# Writing to a file using redirection
echo "---- Redirecting Output to a File ----"
echo "This is a new line." > newfile.txt   # Write to a new file
echo "Redirected output: %d" 42 >> newfile.txt # Append formatted output

# Check if a file exists before performing operations
echo "---- Check if File Exists ----"
if [ -f "newfile.txt" ]; then
    echo "newfile.txt exists. Proceeding with the next operation."
    cat newfile.txt  # Read content of the file
else
    echo "newfile.txt does not exist."
fi

# Using 'tee' to write to a file and also output to terminal
echo "---- Using 'tee' to write to a file and display ----"
echo "This line is written to both file and terminal." | tee file_with_tee.txt

# Using 'find' to locate files
echo "---- Using 'find' to Locate Files ----"
echo "Finding .txt files in the current directory:"
find . -type f -name "*.txt"

# Handling Errors in File Operations
echo "---- Handling Errors in File Operations ----"
non_existent_file="non_existent_file.txt"
if ! [ -f "$non_existent_file" ]; then
    echo "Error: File '$non_existent_file' does not exist." >&2  # Output error to stderr
fi

# Cleanup
echo "---- Cleanup ----"
rm -rf new_directory moved_files          # Remove the created directories
echo "Cleanup complete."

```