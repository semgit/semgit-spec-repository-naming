# Semantic Git Repository Naming 0.1.0

## Summary

Given a PREFIX-TARGET-DESCRIPTION Git repository name, interpret:

- PREFIX as the organization or user identifier
- TARGET as the target platform or audience
- DESCRIPTION as the description of the contents

## Why use semantic names?

When the number of Git repositories in an account grows, it becomes:

- harder to come up with meaningful names for new repositories
- harder to locate existing repositories
- harder to identify repositories

Semantic naming attempts to resolve these issues.

## Quick examples

```bash
# Blog website made with Jekyll
semgit/semgit-web-jekyll-blog

# Blog website made with Ghost
semgit/semgit-web-ghost-blog

# Command line for Node.js
semgit/semgit-node-cli

# API backend written in Go
semgit/semgit-go-api
```

## The PREFIX part

### What?

The prefix identifies the user or organization.

### Why?

This is useful when forking repositories.

#### Without SemGit

```bash
cats/blog
dogs/blog
```

When forking these repositories, they become:

```bash
me/blog
me/blog-1
```

losing all semantic value.

#### With SemGit

```bash
cats/cats-web-blog
dogs/dogs-web-blog
```

When forking these repositories, they become:

```bash
me/cats-web-blog
me/dogs-web-blog
```
retaining all semantic value.

#### How?

Use a short string to identify the user or organization.

## The TARGET part

### What?

The target identifies the target platform or audience for the repository.

### Why?

- allows use of similar descriptions for different targets
- allows easy filtering when searching repositories
- provides immediate semantic context value

### How?

Use a short string to identify the target.

Examples:

- web: website
- node: Node.js application
- go: go application
- spec: specification

## The DESCRIPTION part



