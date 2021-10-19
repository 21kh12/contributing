# :book: Contributing Guidelines
## Table of Contents
- [:book: Contributing Guidelines](#book-contributing-guidelines)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Project Structure](#project-structure)
    - [Prerequisites](#prerequisites)
      - [NodeJS](#nodejs)
      - [TypeScript](#typescript)
      - [React Native](#react-native)
  - [Contributing to the Project](#contributing-to-the-project)
    - [Reporting Security Issues](#reporting-security-issues)
    - [Reporting Bugs or Issues](#reporting-bugs-or-issues)
        - [Bug Checklist](#bug-checklist)
          - [Does this issue pertain to this project?](#does-this-issue-pertain-to-this-project)
          - [Did I cause the issue?](#did-i-cause-the-issue)
          - [Am I using the right version of the required software?](#am-i-using-the-right-version-of-the-required-software)
          - [Has this issue been already reported?](#has-this-issue-been-already-reported)
          - [Is the issue a security related one?](#is-the-issue-a-security-related-one)
    - [Contributing to the Codebase](#contributing-to-the-codebase)
  - [Standards](#standards)
    - [Git Commits](#git-commits)
      - [Commit Syntax](#commit-syntax)
      - [Examples](#examples)
        - [Initial Commit/Starting a new Project](#initial-commitstarting-a-new-project)
        - [Committing/Merging a Feature](#committingmerging-a-feature)
        - [Committing/Merging a Bug Fix](#committingmerging-a-bug-fix)
        - [Committing a Work In Progress](#committing-a-work-in-progress)
        - [Documentation Change](#documentation-change)
        - [Dependency Upgrade](#dependency-upgrade)
        - [Committing/Merging a Build Configuration Change](#committingmerging-a-build-configuration-change)
      - [Notes](#notes)
    - [Git Branches and Pull Requests](#git-branches-and-pull-requests)
      - [Pull Request Review](#pull-request-review)
    - [Code Styling](#code-styling)
  - [Contact Us](#contact-us)

## Getting Started
### Project Structure
Instead of the typical mono-repo structure, this project is broken up into two main repositories
- `spb-http`: this is the back-end that support the Spotify Playlist Builder app. It leverages the Spotify API on behalf of the application and provides a RESTful API for the front-end to consume. It is powered by TypeScript and Express.js.
- `spb-app`: this is the front-end React Native application for the Spotify Playlist Builder. It is the primary user interface for the application and is responsible for displaying the playlist builder UI and handling user interactions.

Both repositories are essential to the functionality of the project. Both of them must work in tandem for the whole project to work.

### Prerequisites
#### NodeJS
The NodeJS runtime is required for the back-end to run. It is recommended to use the latest version of NodeJS. The minimum version supported is 16.x. We suggest you use NVM to manage your NodeJS versions.

You can check your node.js version by using the following command:
```bash
node -v
```

To install NodeJS (with NVM) on any *nix machine, you can use the following commands:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
# if you perfer to use wget:
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# Then save the NVM binary to the path
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

# Install node
nvm install node # node == latest release (what we want!!!)
nvm use node # tell nvm to use this one
# To verify that everything works...
npm version # should contain something like the following:
# {
#   npm: '8.0.x',
#   node: '16.11.x',
#   v8: '9.4.x.x-node.x',
#   ...
# }
# If that is correct, node is properly installed. Move on
```

#### TypeScript
This project uses Typescript (a derivative of Javascript) for both the back-end and the front-end. For more information on what TypeScript is, see the [TypeScript Documentation](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html).

TypeScript and its NodeJS runtime can be installed by using the following command:
```bash
npm install -g typescript ts-node
```

You can use the `ts-node` command just like you would use `node` to run the back-end.


#### React Native
<!-- TODO: [FRONT-END-ST] [PRIORITY] link docs -->
*Coming soon*


## Contributing to the Project
### Reporting Security Issues
First and foremost, if you believe the issue to be one pertaining to security, ***DO NOT OPEN AN ISSUE. REPORT THE BUG DIRECTLY TO US THROUGH EMAIL***

The issue you are reporting is typically a security issue when...
- You can access, view, edit, or in any way alter something that is not yours
- You have discovered something that most likely is not the work of the team, its partners, packages, contributors, verified advertisers or maintainers of the application, in the code repository, or anywhere else
- You have discovered a possible way to abuse the API, application, or server
- Your system has been compromised because of the usage of the application or server

If you have experienced any of the above, this is most likely the result of a possible security risk and should be reported. Failure to report could result in possible legal action on our behalf. Even if your issue does not meet the above and still believe it is a security related issue, do not hesitate to email us. It’s better to be safe rather than to be sorry.

### Reporting Bugs or Issues
##### Bug Checklist
Please check the following to ensure that you are cleared to open an issue.

###### Does this issue pertain to this project?
If your issue has to do with the NodeJS/TypeScript runtime, any of the packages/software that is not covered/maintained by the team, or anything else, then this is not the proper place to file your issue with. If you need help being directed to the proper bug tracker or troubleshooting guide, feel free to contact us. (See [Contact Us](#contact-us))

###### Did I cause the issue?
If you have modified any of the source, there is a high probability that the issue has been caused by tampering. If the issue still persists after reverting your code, open an issue.

###### Am I using the right version of the required software?
We do not support old software. Please check your versions against the ones specified in the `main` branch's `package.json`/`package-lock.json` and in the [Pre-requisites Section in our Contributing guide](#prerequisites).

###### Has this issue been already reported?
If the issue has already been reported and it is still open on our GitHub, please comment your issue rather than opening a new issue. If it is not still open check the status of it. If it has the `wont-fix` tag attached to the issue, do not bring it up again unless you see it as a prominent issue and a significant amount of time has passed. Also check to see if there is a solution. Sometimes issues will be closed not because they were marked as invalid or a solution was reached but because of a lack of activity. If you find this to be the case, feel free to request the issue to be re-opened.

###### Is the issue a security related one?
If you issue relates to security, please see [Reporting Security Issues](#reporting-security-issues).

### Contributing to the Codebase
If you are contributing to the codebase (does not include documentation), please make sure to follow our [standards](#standards).

Please check if there are already any issues open that can be resolved. If not, make sure that a pull request doesn't already cover what you are attempting to merge.


## Standards
### Git Commits
For the sake of consistency, we use a committing standard that you might be unfamiliar with. We loosely follow the [Git Commit Conventions](https://conventionalcommits.org/en/v1.0.0-beta.0/). This is a set of guidelines for how to commit to the codebase. We also use the [Gitmoji Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=Gitmoji.gitmoji-vscode) which places an emoji before each commit to help identify and sort commits based on statuses/types. If you are confused, below will be a list of example commits.
#### Commit Syntax
The following is a summation of the syntax that we use for commits:
```
<emoji> <type: chore (build | ci | deps | docs) | feat | fix | wip >: <verb> <subject>
```
#### Examples
##### Initial Commit/Starting a new Project
```
🎉 chore: initial commit
```
##### Committing/Merging a Feature
```
✨ feat: implement Spotify OAuth integration
```
##### Committing/Merging a Bug Fix
```
🐛 fix: fix #147, stop Spotify from returning a 404 on playlist requests
```
##### Committing a Work In Progress
This is good for large features that you may need to commit more than once for.
```
🚧 wip: add support for Spotify Web API
```
##### Documentation Change
```
📝 chore(docs): update README.md
```
##### Dependency Upgrade
```
⬆️ chore(deps): update dependencies to latest versions
```
##### Committing/Merging a Build Configuration Change
```
🔧 chore(build): update build configuration
```
#### Notes
While this isn't strictly enforced, blatant violation of these guidelines will result in a prohibitive "false commit" status being assigned.

### Git Branches and Pull Requests
We use [GitHub](https://github.com) for our codebase. We use branches for development and releases. We use pull requests for feature/bug fixes. We use pull requests internally for features and bug fixes that are not ready to be merged into the main branch.

We follow a system similar to GitFlow. If you are unfamiliar with GitFlow, see the [helpful docs guide on Atlassan](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). We modify it in a slight way. Feature branches are developed on their own branches (typically named `feat-<feature name>`). Bug fixes are developed on their own branches (typically named `fix-<bug number>`, hotfixes get their own special branch name of `hot-<bug number>`). The features branch is the branch that is merged into the main branch and tagged with their release version.

It looks something like this:
```
    main:       A ----------------------------------------- 1.1.0 --------- 1.1.1 --- 1.0.2
                 \                                         /     \         /      \ /
    hotfixes:     \                                       /       \       /        N
                   \                                     /         \     /          \
    features:       B --- C --- D --- G --- H --- J --- L --------- \ - / ---------- O
                           \        /        \        /              \ /
    fixes:                  E --- F --------- I --- K --------------- M

```

While it looks very daunting, it is quite simple once you get used to it.

The only exceptions to this is if you are working on a repo separate from the main two repos (ie. documentation or packages). In that case, you can use the `main` branch for development.

#### Pull Request Review
While it is not required, pull request reviews should be done. Branches should be not merged unless CI/Testing has passed.

### Code Styling
lol idc enough

## Contact Us
You can contact us over the KnightHacks Discord server. Simply mention a Team 12 member by using `@12` and then pressing <kbd>Tab</kbd>.

