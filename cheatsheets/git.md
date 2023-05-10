# Git
## Repository
### Init
```bash
git init                    # Creates an empty repository
```

## Snapshots
### Status
```bash
git status                  # Displays the status of each modified file
git status -s               # Short status version with columns to represent index and working directory
```

## Add
```bash
git add file.txt            # Adds a file to the staging area
git add file.txt file.md    # Adds multiple files
git add *.txt               # Add all files with the pattern
git add .                   # Add all changes in the current directory
```

### Commit
```bash
git commit -m "Descrition"  # Creates a commit with a short message
git commit                  # Opens an editor to type a short message and a description
git commit -am "Message"    # Commits directly, without staging the files
```

### Remove
```bash
git rm file.txt             # Removes a file from index and working directory
git rm file.txt file.md     # Removes multiple files
git rm *.txt                # Removes files with a pattern
git rm --cached file.txt    # Removes a file from the index only
```