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
    - [Dif](#diff)
- [History](#history)
    - [Log](#log)
    - [Show](#show)
    - [Ls-tree](#ls-tree)
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

### Show
```bash
git show <commit's identifier>  # Displays the changes in a commit
git show HEAD                   # Displays the contents from the latest commit
git show HEAD~<number>          # Displays the nth commit from the HEAD
git show HEAD~1:<path to file>  # Displays a specific version of file stored in the commit
```

### Ls-tree
```bash
git ls-tree                     # Displays all the files of a commit in a tree
git ls-tree HEAD~<number>       # Displays the files of a specific commit
```
