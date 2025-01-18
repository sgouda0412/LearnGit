```git
# Initialize a new repository
git init  # Creates a new git repository in the current directory

# Clone an existing repository
git clone <repository_url>  # Clone a remote repository to your local machine

# Check the current status of your repository
git status  # Displays the state of the working directory and staging area

# Add files to the staging area
git add <file_name>  # Add specific file to staging area
git add .  # Add all files in the directory to the staging area

# Commit changes to the repository
git commit -m "Commit message"  # Commit the staged changes with a descriptive message

# Push changes to a remote repository
git push origin <branch_name>  # Push the local changes to the remote branch
*main* *branch-name*

# Pull changes from a remote repository
git pull origin <branch_name>  # Fetch and merge changes from the remote repository

# View the commit history
git log  # Shows the commit history in the current branch


git log --oneline --graph --pretty=format:"%C(yellow)%h%C(reset) %C(cyan)%d%C(reset) %C(bold)%s%C(reset) %C(magenta)[%an] %C(blue)(%cr)"


# View the differences between your working directory and staged files
git diff  # Shows changes between the working directory and the index (staging area)

# Create a new branch
git branch <branch_name>  # Creates a new branch in the repository

# Switch to a different branch
git checkout <branch_name>  # Switch to an existing branch

# Create and switch to a new branch in one command
git checkout -b <branch_name>  # Creates a new branch and checks it out

# Merge a branch into the current branch
git merge <branch_name>  # Merges changes from another branch into the current branch

# Delete a branch locally
git branch -d <branch_name>  # Deletes a branch, but only if it has been fully merged

# Push a new branch to a remote repository
git push origin <branch_name>  # Pushes a new branch to the remote repository

# Add a remote repository
git remote add origin <repository_url>  # Adds a new remote URL to your local repository

# View the remote repositories
git remote -v  # Shows the list of remote repositories

# Remove a remote repository
git remote remove <remote_name>  # Removes a remote repository from your configuration

# Unstage a file (remove from staging area)
git reset <file_name>  # Removes a file from the staging area, keeping local changes

# Discard changes in a file (restore to last commit)
git checkout -- <file_name>  # Discards local changes to a file and restores the last committed version

# Reset the repository to a previous commit (hard reset)
git reset --hard <commit_id>  # Resets the repository to a specific commit, losing all changes after it

# Revert a commit (create a new commit that undoes the changes)
git revert <commit_id>  # Reverts changes from a specific commit and creates a new commit

# Stash changes temporarily
git stash  # Stashes your local changes so you can work on something else without committing

# Apply stashed changes
git stash apply  # Applies the most recent stashed changes

# List all stashes
git stash list  # Shows a list of all stashed changes

# Drop a stash
git stash drop  # Removes a stash from the stash list

# Create a tag for a commit
git tag <tag_name>  # Creates a lightweight tag pointing to the current commit

# Push a tag to the remote repository
git push origin <tag_name>  # Pushes a tag to the remote repository

# List all tags
git tag  # Lists all tags in the current repository

# Set global user name for commits
git config --global user.name "Your Name"  # Configures the global username for commits

# Set global user email for commits
git config --global user.email "your_email@example.com"  # Configures the global email for commits

# Set default editor for Git
git config --global core.editor "nano"  # Configures the default text editor for Git (nano in this case)

# View the Git configuration
git config --list  # Displays the current Git configuration settings

# Show the differences between two commits
git diff <commit_id_1> <commit_id_2>  # Shows the differences between two commits

# Check which files are being tracked by Git
git ls-files  # Shows all files that are currently tracked by Git

# View the remote repository URL
git remote show origin  # Displays the URL and additional information about the remote repository

```
