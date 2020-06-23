# Git

## Introduction

Git is a distributed version control system created by Linus Torvalds, which is commonly used in open source community and commercial companies.

To have a better understanding of Git, here I recommend [Pro Git](https://github.com/progit/progit2). It is an open source book in various languages and you may also buy a paper book.

## Installation

```bash
brew install git
```

## Configuration

```bash
git config user.name "David Zhang" # it's me
git config user.email "me@crisp.dev"
```

## Quick Start

The basic workflow of Git is `clone-add-commit-push`.

Add file\(s\) to index:

```bash
# add single file
git add /path/to/file
# add files by patterns
git add .
git add *.go
# add all
git add -A
```

Commit:

```bash
git commit -m "feat: my commit msg"
```

ps: to make commit message "human and machine readable", [Conventional Commit Format](https://www.conventionalcommits.org/) is highly recommended here.

Amend Commit:

```bash
git commit --amend
```

Reset Autor:

```text
git commit --amend --reset-author
```

Branch:

```bash
# Create a branch, `git checkout -b` is also available
git switch -c <branch-name>

# Switch branch
git switch <branch-name>

# Show branches
git branch -l

# Delete branch
git branch -d <branch-name>

# Rename branch
git branch -m <branch-name> <new-branch-name>

# Push to branch
git push origin <branch-name>

# Pull from branch
git pull origin <branch-name>
```

## Advanced Usage

Git is a very complicated tool when we look at it from a user interface \(CLI\) scope. It may break down sometimes and we just do not have enough knowledge about Git at that time.

Before we dive into how Git works internally systematically, here I recommend a great online book called "[Flight Rules for Git](https://github.com/k88hudson/git-flight-rules)". It is a guide for programmers \(like the pilot\) to handle what to do when things go wrong. Simply tell what the situation is and what you want to achieve, and then follow the rules provided by the guide.

However, there are also some commands that are commonly used when we step off basic level.

Stash:

Rebase:

Force Push:

```text
# Force push and it may mess up the remote
git push --force

# 
git push --force-with-lease
```

Reset:

```bash
# Cancel `git add`
git reset HEAD

# Cancel last commit
git reset HEAD~

# Cancel last N (e.g. 3) commit
git reset HEAD~3

# Reset to HEAD --hard, so commits would lose
git reset --hard
```

`git reset` is kind of dangerous, you may lose codes or files from it. But for things already have committed, don't be so worry because `git reflog` could save you even if you screw it up.

Cherry Pick:

```bash
git cherry-pick <commit-hash>
```

Clean:

```bash
# Clean the workspace, untracked files would be deleted
git clean -f -d
```

