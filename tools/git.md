[Home](../index.md) > Tools > [Git](./git.md)

# Tools | Git

## .git folder.

`.git/objects/` - contains all commit objects, in a hashed directory structure.

`.git/refs/` - contains references to commits, such as branches and tags.

`.git/logs/` - contains history logs of changes.

```text
# Inspect any object by sha
git cat-file -p <sha>
```

## Configuration

```text
# List all config settings.
git config --list --show-origin

# Find keys
git config --list | grep <search_text>

# Read config value.
git config --get <section>.<key>

# Set config value for all users.
git config --global <section>.<key> <value>

# Add new config key.
git config --add <section>.<key> <value>

# Unset key(s)
git config --unset-all <section>.<key>

# Remove section.
git config --remove-section <section>
```

## Basics

```text
# Init repo.
git init

# View state
git status

# Stage file(s)
git add .
git add -A
git add <path to file | pattern>

# Un-stage file(s)
git rm --cached <path to file | pattern>

# Commit staged changes
git commit -m '<meaningful commit message>'

# Viw commit history.
git log
git log --graph --decorate
git log --graph --oneline --decorate --all
```

## Branching

```text
# List all branches
git branch
git branch --list

# Create new branch
git branch <branch_name>

# Create and/or switch
git checkout <branch_name>

# Delete branch
git branch -D <branch_name>
```
