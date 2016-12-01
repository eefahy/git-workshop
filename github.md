GitHub
===============

  - [Bare Repositories](#bare-repositories)
  - [Authentication](#authentication)
  - [Issues](#issues)
  - [Workflows](#workflows)
  - [Commit Messages Best Practice](#commit-messages-best-practice)
  - [Tags and Releases](#tags-and-releases)
  - [All Together Now](#all-together-now)


### Bare Repositories
GitHub makes available something called _bare repositories_ for the purpose of storing, publishing, and sharing files. Bare repositories do not have working directories or specific checked out versions of the code itself but rather operates as the centralized repository for managing access and collaboration.


### Authentication
GitHub uses SSH keys to authenticate computers to GitHub user accounts. If you don't already have a SSH key made, create one by running:  
`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

Then [upload your SSH Key](https://github.com/settings/keys) to your GitHub account and test access to your account by running:  
`ssh -T git@github.com`

If everything is properly configured you should get:
```
Hi username! You've successfully authenticated, but GitHub does not
provide shell access.```


### Issues

Each GitHub repository automatically gets an Issues interface to track, document, and discuss issues regarding bugs, feature requests, technical debt, etc. Issues can have labels, milestones, and assignees.

General guidelines for submitting an issue:
  - review existing issues before submitting a new one to avoid duplication
  - provide a detailed title and description that outlines the problem
  - describes expected vs actual behavior
  - details how to reproduce the behavior and/or screenshots or demos displaying the problem
  - provide any error messages or helpful log output
  - include system details like specific versions, operating systems. etc.
  - reference related or preexisting issues
  - provide an estimated fix time
  - description of the business value or related importance of the proposed change

There's a lot more to issues, including the ability to link issues between separate repos, close issues with comments in pull requests, and solicit others to weigh in on issue discussion but @mentions and notification settings. See [GitHub's Guide to Issues](https://guides.github.com/features/issues/) for more information.


### Workflows

GitHub offers a bunch of features to collaborate on your files and as a result, various workflows have developed around those features. Each workflow differs on its prescribed branching schemes and the deployment concerns around them, but generically, most workflows assume that the `master` branch should be protected and always in a deployable state. The most important aspect of workflows though is that it's agreed upon within the core committers and well documented for external contributors.

One light-weight workflow is [GitHub Flow](https://guides.github.com/introduction/flow/) which leverages the features in GitHub like Pull Requests to encourage transparency and collaboration.


### Commit Messages Best Practice

Commit messages are incredibly helpful when they are well written. They serve at least three important purposes:
 - speeds up code review
 - aids in release summaries
 - helps your future self understand the rationale behind why specific changes were made within the code base

The original message template from [Git documentation](https://git-scm.com/book/ch5-2.html) is as follows:
```
Short (50 chars or less) summary of changes

More detailed explanatory text, if necessary.  Wrap it to about 72
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Further paragraphs come after blank lines.

  - Bullet points are okay, too

  - Typically a hyphen or asterisk is used for the bullet, preceded by
  a single space, with blank lines in between, but conventions vary
  here```

If a summary of the change is too difficult to describe, it might be a sign of the commit being too big and should therefore be broken down in to multiple commits using `git add -p`


### Tags and Releases

Tags come in two flavors: light-weight and annotated.

A light-weight tag is just a pointer to a specific commit. Therefore it's like a branch that never changes. Light-weight tags are usually meant to be temporary for sharing or quick reference.

Annotated tags are, yep, annotated. That means they get an author name and date, a message, and an id. Annotated tags are usually what you want if you intend to cut a release based on a tag.

Tagging your code works hand in hand with publishing a release. Once a tag is created on a branch, releases can be made through the GitHub UI.


### All Together Now

Test out your ability to do the following:
  - [ ] Create an issue
  - [ ] Fork a repo
  - [ ] Create a branch (with the issue number in the branch name)
  - [ ] Make some commits
  - [ ] Rebase (clean up) your commits
  - [ ] Push your branch to your fork
  - [ ] Create a Pull Request
  - [ ] Get some advice/revise code if necessary
  - [ ] Create a tag and a release
