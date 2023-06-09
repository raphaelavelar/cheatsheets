# Git
## Table of contents
- [Repository](#repository)
    - [Init](#init)
- [Configuration](#configuration)
    - [User](#user)
    - [Alias](#alias)
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
    - [Show](#show)
    - [Ls-tree](#ls-tree)
    - [Bisect])(#bisect)
    - [Shortlog](#shortlog)
    - [Blame](#blame)
    - [Tag](#tag)
---

## Repository
### Init
```bash
git init                        # Creates an empty repository
```

## Configuration
### User
```bash
# Git offers three configuration levels:
# System: applies to all users
# Global: applies to every repository of the current user
# Local: applies to the current repository
git config --global user.name "name"    # Configures the user's name globally
git config --global user.email "email"  # Configures the user's email globally
```

### Alias
```bash
git config --global alias.<alias> "command" # Configures an alias for a git command
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
git restore --source=HEAD~<number> <path to file> # Restores a file from a specific commit
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
git diff HEAD~<n> HEAD~<m>      # Displays the changes between the specified commits
git diff HEAD~<n> HEAD~<m> <path to file>   # Displays the changes for a file between the specified commits
```

## History
### Log
```bash
git log                         # Lists commits by newest
git log --oneline               # Summarized list of commits
git log --oneline --reverse     # Summarized list of commits ordered by oldest
git log --stat                  # Lists changes statistics of each commit
git log --patch                 # Lists changed files in each commit
git log --all                   # Lists all commits when in a detached HEAD state
git log -<number>               # Lists n commits
git log --author="Name"         # Filter by author
git log --before="Date"         # Filter by creation date before a specified date
git log --after="Date"          # Filter by creation date after a specified date
git log --grep="text"           # Filter by a text in commit message
git log -S"text"                # Filter by a word in files
git log <hash>...<hash>         # Lists commits between the first and second hash specified, exclusive
git log <path to file>          # Lists commits that modified the specified file 
git log --pretty=format:"args"  # Formats the commit list following a pattern. See more on https://git-scm.com/docs/git-log
```

### Show
```bash
git show <commit's identifier>  # Displays the changes in a commit
git show HEAD                   # Displays the contents from the latest commit
git show HEAD~<number>          # Displays the nth commit from the HEAD
git show HEAD~1:<path to file>  # Displays a specific version of file stored in the commit
git show HEAD~1 --name-only     # Displays only the name of the modified files
git show HEAD~1 --name-status   # Displays the name and status of each modified file
```

### Ls-tree
```bash
git ls-tree                     # Displays all the files of a commit in a tree
git ls-tree HEAD~<number>       # Displays the files of a specific commit
```

### Bisect
```bash
# Bisect divides the history in half based on good and bad commits in order to identify a
# problem added to the sourde code.
# After starting it, it's necessary to specify the good and bad commits using their unique identifiers
# Once this configuration is done, the current state should be tested to mark it accordingly.
git bisect start                # Starts bisect
git bisect bad                  # Sets the HEAD as a bad commit
git bisect good                 # Sets the HEAD as a good commit
git bisect reset                # Resets the HEAD to master
```

### Shortlog
```bash
# Shortlog accepts the same filters as the log command, e.g. author, before and after
git shortlog                    # Lists contributors and their commits
git shortlog -s                 # Lists contributors and their number of commits
```

### Blame
```bash
git blame <path to file>        # Lists authors and commits that modified each line of file
git blame -e <path to file>     # Lists authors' emails instead of names
git blame -L <n>, <m> <file>    # Lists authors and commits that modified the lines n to m of a file
```

### Tag
```bash
git tag                         # Lists existing tags
git tag -n                      # Lists existing tags and their messages
git tag <name>                  # Creates a tag in HEAD
git tag <name> <commit>         # Creates a tag for a specific commit
git tag -a <name> -m "message"  # Creates an annotated tag with a custom message
git tag -d <tag name>           # Deletes a tag
git show <tag name>             # Provides detailed information for a tag
```
