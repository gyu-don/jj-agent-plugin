# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This project provides jj (Jujutsu) skills and hooks for Claude Code and compatible AI agents. It enables AI assistants to work effectively with jj version control instead of git.

## About jj (Jujutsu)

Jujutsu is a modern version control system that is compatible with Git repositories but uses different concepts:
- **Bookmarks** instead of branches (use `jj bookmark` commands)
- **Working copy** is always a commit that can be modified
- **Change IDs** are stable identifiers for commits across rebases
- No staging area - all changes are automatically tracked

## Common Commands

```bash
# Status and history
jj status                    # Show working copy status
jj log                       # Show commit history
jj diff                      # Show changes in working copy

# Creating and modifying commits
jj new                       # Create new empty commit
jj commit -m "message"       # Finalize current commit with message
jj describe -m "message"     # Set/update commit message
jj squash                    # Squash into parent commit

# Bookmarks (like git branches)
jj bookmark create name      # Create bookmark at current commit
jj bookmark set name         # Move bookmark to current commit
jj bookmark list             # List all bookmarks

# Working with remotes
jj git fetch                 # Fetch from remote
jj git push                  # Push to remote
```

## Key Differences from Git

- Use `jj bookmark` instead of `git branch`
- Use `jj new` to start new work (creates empty commit)
- Use `jj describe` to set commit messages
- Changes are automatically tracked (no `git add` needed)
- Use `jj git push` and `jj git fetch` for remote operations
