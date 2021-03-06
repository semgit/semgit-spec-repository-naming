# SemGit Repository Naming

Specification for Semantic Git Repository Naming.

## The problem

When adding Git repositories to a Git account, repository naming can quickly become a mess:

- coming up with meaningful names for new repositories becomes challenging
- locating existing repositories becomes cumbersome
- identifying repositories becomes hard

A lack of consistency can cause a lot of headaches and a serious loss of time and money, especially in organizations with a large number of repositories and team members.

Semantic naming attempts to resolve these issues.

## The proposed solution

Given a `prefix-target-description` Git repository name, interpret:

- `prefix` as the organization or user identifier
- `target` as the target platform or audience
- `description` as the description of the contents

Only lowercase characters and hyphens are used.

## Quick example

#### Without SemGit

Repositories are hard to identify for people that didn't create them:

```bash
blog
blog-1
clientApplication
deploymentcli
private-api
public-api
website
web_server
```

#### With SemGit

Repositories are easier to identify and can be sorted alphabetically to group them:

```bash
# Go applications
semgit-go-private-api
semgit-go-public-api

# Node applications
semgit-node-deployment-cli
semgit-node-web-server

# Websites
semgit-web-ghost-developer-blog
semgit-web-corporate-website
semgit-web-jekyll-blog

# WinRT application
semgit-winrt-client-application
```

## The PREFIX part

### What?

The prefix identifies the user or organization.

### Why?

This is useful when forking repositories.

#### Without SemGit

The repository names are changed during the fork process to prevent name collisions:

```bash
cats/blog              --> me/blog
dogs/blog              --> me/blog-1
```

#### With SemGit

The original repository names are retained:

```bash
cats/cats-web-blog     --> me/cats-web-blog
dogs/dogs-web-blog     --> me/dogs-web-blog
```

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

Contributors:

- [Stefan Lapers](http://stefan.lapers.be/)

If you'd like to leave feedback, please [open an issue on GitHub](https://github.com/semgit/semgit-spec-repositories/issues).

## License

[Creative Commons](http://creativecommons.org/licenses/by/3.0/).

