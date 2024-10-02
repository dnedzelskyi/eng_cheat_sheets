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
git reset
git reset <path to file | pattern>

# Remove tracking file(s)
git rm --cached <path to file | pattern>

# Commit staged changes
git commit -m '<meaningful commit message>'

```

## History & Logs

```text
# Inspect object by sha
git show sha

# Inspect commit
git show --name-status <sha>

# Commit staged changes
git commit -m '<meaningful commit message>'

# Viw commit history.
git log
git log -<n_last_commits>
git log --graph --decorate
git log -p --graph --decorate --all
git log -p --graph --decorate --all --oneline

# View HEAD history.
git reflog

```

## Branching

```text
# List all branches
git branch
git branch --list

# Create new branch
git branch <branch_name>

# Switch branch
git checkout <branch_name>

# Create and switch branch
git checkout -b <branch_name>

# Delete branch
git branch -D <branch_name>
```

## Merging

```text
# Merge some source branch onto active branch
git merge <source_branch>
```

## Rebase

```text
# Rebase active branch on some target branch
git rebase <target_branch>
```

> ⚠️ Warning.
>
> Never rebase public branches to avoid history changes.
> All rebase mainly for private/local branches.

## Cherry pick

```text
# Cherry pick and commit.
git cherry-pick <commit_sha>

# Pull changes without committing it.
git cherry-pick --no-commit <commit_sha>
```

## Git Remote

```text
# View remotes remote_names and uris
git remote -v

# View all branches with remote ones.
git branch -a

# Add new remote repo
git remote add <remote_name> <uri>
git remote add origin https://github.com/user/repo.git
git remote add origin /home/project-foo

# Show info about specific remote
git remote show <remote_name>

# Fetch all/specific branches and data from remote(s)
git fetch
git fetch <remote_name>
git fetch <remote_name> <branch>

# Check if branch associated with remote.
git branch -vv

# Create new branch with tracking.
git checkout <remote_branch>
git checkout -b <local_branch> <remote_name>/<remote_branch>

# Set up tracking for existing branch.
git branch --set-upstream-to=<remote_name>/<remote_branch> <local_branch>
git pull <remote_name> <remote_branch> -u

# Pull = (fetch + merge) from remote.
git pull
git pull <remote_name> <remote_branch>
git pull --rebase <remote_name> <remote_branch>

# Push to remote.
git push
git push --dry-run
# Push new branch and set upstream.
git push -u <remote> <branch>

```

> ✏️ Tip
>
> Remotes naming
>
> - _origin_ - for main upstream repo
> - _upstream_ - for repo fork
> - _descriptive name_ - in case of multiple remotes (github, gitlab ...)
