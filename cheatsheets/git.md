# Git
## Table of contents
- [Repository](#repository)
    - [Init](#init)
- [Snapshot](#snapshot)
    - [Status](#status)
    - [Add](#add)
    - [Commit](#commit)
    - [Restore](#restore)
    - [Remove](#remove)
    - [Move](#move)
    - [Clean](#clean)
    - [Diff](#diff)
- [History](#history)
    - [Log](#log)
---

## Repository
### Init
```bash
git init                        # Creates an empty repository
```

## Snapshot
### Status
```bash
git status                      # Displays the status of each modified file
git status -s                   # Short status with columns to represent index and working directory
```

## Add
```bash
git add file.txt                # Adds a file to the staging area
git add file.txt file.md        # Adds multiple files
git add *.txt                   # Add all files with the pattern
git add .                       # Add all changes in the current directory
```

### Commit
```bash
git commit -m "Descrition"      # Creates a commit with a short message
git commit                      # Opens an editor to type a short message and a description
git commit -am "Message"        # Commits directly, without staging the files
```

### Restore
```bash
git restore .                   # Restores all modifications in the current directory
git restore --staged file.txt   # Restores a file in index
```

### Remove
```bash
git rm file.txt                 # Removes a file from index and working directory
git rm file.txt file.md         # Removes multiple files
git rm *.txt                    # Removes files with a pattern
git rm --cached file.txt        # Removes a file from the index only
```

### Move
```bash
git mv file.txt newFile.txt     # Moves and rename a file
```

### Clean
```bash
git clean -fd                   # Cleans all unstracked files
```

### Diff
```bash
git diff                        # Displays all changes
git diff --staged               # Dsiplays changes on index
```

## History
### Log
```bash
git log                         # List of commits
git log --oneline               # Summarized list of commits
git log --oneline --reverse     # Summarized list of commits ordered by first commit
```