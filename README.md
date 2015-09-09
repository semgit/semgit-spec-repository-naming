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
# Websites
semgit/semgit-web-jekyll-blog
semgit/semgit-web-ghost-developer-blog
semgit/semgit-web-corporate-website

# Node applications
semgit/semgit-node-deployment-cli
semgit/semgit-node-web-server

# Go applications
semgit/semgit-go-public-api
semgit/semgit-go-private-api

# Yeoman generators
semgit/semgit-yeoman-generator-contract
semgit/semgit-yeoman-generator-web-application
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

A few examples:

| Target name | Target description   |
| --- | --- |
| angular | Angular library |
| docs | Documentation |
| go | Go application |
| less | LESS stylesheets |
| node | Node.js application |
| sass | Sass stylesheets |
| spec | Official specificiation |
| web | Website |

## The DESCRIPTION part

### What?

The description part describes the main contents of the repository.

### Why?

- identify the repository

### How?

Use a string to identify the main contents. Try to use a name that is not dependent on external factors:

**bad**: `semgit-web-www-semgit-org`
**good**: `semgit-web-corporate-website`

The reason `www-semgit-org` is bad is because it may require a Git repository name change when the url of the website changes. Use a name that is not likely to change when external factors (such as a URL) change.



