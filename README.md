# Semantic Git Repository Naming 0.1.0

When adding Git repositories to a Git account, repository naming can quickly become a mess:

- coming up with meaningful names for new repositories becomes challenging
- locating existing repositories becomes cumbersome
- identifying repositories becomes hard

A lack of consistency can cause a lot of headaches and loss of time and money.

Semantic naming attempts to resolve these issues.

## Anatomy of a SemGit repository name

Given a `prefix-target-description` Git repository name, interpret:

- `prefix` as the organization or user identifier
- `target` as the target platform or audience
- `description` as the description of the contents

Only lowercase characters and hyphens are used.

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

# WinRT application
semgit/semgit-winrt-client-application
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

- **bad**: `semgit-web-www-semgit-org`
- **good**: `semgit-web-corporate-website`

Avoid `www-semgit-org` because it may require a Git repository name change when the url of the website changes. Use a name that is not likely to change due to external factors.

## FAQ

##### If it's best not to use URL's in Git repository names, how can I quickly locate a repository in GitHub when I only know the website's name?
To optimize search results in sites like GitHub, you can specify the website url in the GitHub repository description. This allows others to quickly locate the correct repository. For example:

- GitHub repository name: `semgit-web-corporate-website`
- GitHub repository description: "Website hosted on http://www.semgit.org"

When searching for "semgit.org" in GitHub, the correct repository will shop up. And when the URL of the website changes, no repository name change is required. You can just update the repository description in GitHub.

## Author

The SemGit specification is authored by [Jurgen Van de Moere](http://www.jvandemo.com).

If you'd like to leave feedback, please [open an issue on GitHub](https://github.com/semgit/semgit-spec-repositories/issues).

## License

[Creative Commons](http://creativecommons.org/licenses/by/3.0/).

