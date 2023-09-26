# Technologies used in the frontend

## React

- React is widely used in frontend development due to its focus on creating reusable components and its ability to handle efficient updates. It facilitates the creation of dynamic and modern user interfaces.
- It uses a component-based model to break down the user interface into reusable and easy-to-maintain parts.

## TypeScript

- TypeScript adds a static type system to JavaScript, helping detect errors before runtime and facilitating collaboration in large projects.
- It provides a safer and more robust way to develop applications, especially in team environments.

## Vite
- Vite is a fast and flexible web development environment that provides a real-time development server and efficient module loading.
- It enables instant browser reloading and optimized production builds.

## Node.js

- Node.js is a JavaScript runtime environment on the server side.
- It allows the creation of web servers, route handling, processing HTTP requests, accessing databases, and other server-side operations.
- It is particularly suitable for real-time applications and REST APIs due to its efficient handling of concurrent connections.

## Jest
- Jest is a testing framework designed for fast tests.
- It is compatible with TypeScript.

## Installation of dependencies
### Node.js
1. Open the following link https://nodejs.org/es, download the LTS version, and install it.
2. UTo fetch the latest dependencies, update NPM (the Node Package Manager) using the following command:

```bash
npm install -g npm@latest
```

3. Install Create React App, which is a command-line interpreter (CLI) that allows us to easily set up React and includes Webpack for project compilation and minification, live reload functionality, a basic structure for ReactJS projects, use the next command:

```bash
npm install -g create-react-app
```
### Vite
1. Run the following command at the root of your project to install Vite as a local dependency:

```bash
npm install vite --save-dev
```
# Steps to start working on this project

## Commands to start the project
1. Clone the GitHub repository using the following command:
```bash
git clone https://github.com/ioet/ioet-snack-app-frontend.git
```
2. Create the .env file in the following path: ioet-snack-app-frontend/
3. In the .env file you should define the environmental variables (ask the team for the variables).
4. Run the following command in this path: ioet-snack-app-frontend/
```bash
npm run dev
```

## How to run the lint
Use the following command:
```bash
npm run lint
```
If you need correct the linters, use the next command:
```bash
npm run lint:fix
```

## How to run the tests

Use the following command:
```bash
npm run test
```


# How to contribute to the project

Version control and proper commit practices are crucial for managing software projects effectively. Combining commits with Semantic Versioning (SemVer) helps maintain a clear history of changes and enables developers to communicate the impact of updates clearly. This guide will walk you through the process of using commits and SemVer together in your development workflow.

## Version Control System

First, ensure that you have set up a version control system (VCS) such as Git for your project. Git allows you to track changes, collaborate with others, and manage your codebase efficiently.

## Commits Standard

Follow these [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/#summary) guidelines to align your versioning with SemVer:

**1. Commit Scope:** Prefix your commit messages with a scope to indicate the type of change you are making. Common scopes include:

- **feat:** A new feature (will increment MINOR version).
- **fix:** A bug fix (will increment PATCH version).
- **perf:** A code change that improves performance (will increment PATCH version).
- **build:** Changes that affect the build system or external dependencies (e.g., npm, ts configuration) (no version change).
- **ci:** Changes to your CI or CD configuration files and scripts (e.g., Azure DevOps, GitHub Actions) (no version change).
- **docs:** Documentation-only changes (no version change).
- **refactor:** A code change that neither fixes a bug nor adds a feature (no version change).
- **style:** Changes that do not affect the meaning of the code (e.g., typos, white-space, formatting) (no version change).
- **test:** Adding missing tests or correcting existing tests (no version change).

**2. Commit Description:** Write a clear and concise commit message that explains the change. Use the imperative mood (e.g., "Add," "Fix," "Update") to describe what the commit does.

**3. Breaking Changes:** If your commit includes a backward-incompatible change (MAJOR version), add a footer to the commit message with a **BREAKING CHANGE** tag and a description of the change.

## Version Incrementation using Semantic Versioning (SemVer)

As a quick reminder, [Semantic Versioning (SemVer)](https://semver.org/) consists of three parts: **MAJOR**, **MINOR**, and **PATCH**. Increment these versions based on the type of changes and use the commit messages to determine the appropriate version increment:

1. **MAJOR:** For backward-incompatible changes. If any commit message includes a **BREAKING CHANGE**, increment the MAJOR version.
2. **MINOR:** For backward-compatible feature additions. If there are commits with new features (**feat** scope) but no **BREAKING CHANGE**, increment the MINOR version.
3. **PATCH:** For backward-compatible bug fixes. If there are only bug fixes (**fix** scope), performance improvements (**perf** scope), or other non-breaking changes, increment the PATCH version.

## Specifying Versioning

You can specify versioning for your software project in various ways:

**1. package.json File:** In JavaScript and Node.js projects, you can specify the version in the package.json file under the "version" field.

**2. Source Code File:** You can define the version as a variable in one of your source code files. For example, in Python, you can have a __version__ variable in a Python file.

**3. Dedicated Version File:** Create a separate file (e.g., version.txt or VERSION) that contains the version number as plain text.

**4. Environment Variable:** Set an environment variable to represent the current version, and your code or build scripts can access it when needed.

**5. Git Tags:** Use annotated Git tags to mark specific versions of your project.

**6. Continuous Integration (CI) Tools:** Some CI/CD (Continuous Integration/Continuous Deployment) tools allow you to set and manage versioning information as part of the build and release process.

**7. Build Systems:** Some build systems allow you to specify version information as part of the build configuration.

**8. Custom Configuration Files:** If your project has a custom configuration file, you can include versioning information within it.

**9. Database:** In some cases, versioning information may be stored in a database for applications that require version tracking.

**10. Version Management Tools:** There are tools and libraries available that are specifically designed to manage versioning for software projects.

## Example Workflow

Let's go through an example workflow with more realistic commit messages:

**1.** You start your project at version **1.0.0**.
**2.** Adding a new feature (MINOR):

```bash
git commit -m "feat: Add user authentication."
```
This commit adds a new feature, so it will trigger a MINOR version increment. For example, if your project is currently at version 
**1.0.0**, this commit would update the version to **1.1.0**.

**3.** Fixing a bug (PATCH):

```bash
git commit -m "fix: Fix validation bug in the registration form."
```
This commit addresses a bug, so it will trigger a PATCH version increment. For example, if your project is currently at version 
**1.1.0**, this commit would update the version to **1.1.1**.

**4.** Documentation update (No version change):

```bash
git commit -m "docs: Update README."
```
This commit includes documentation changes but doesn't trigger a version change. It's useful for keeping the documentation up to date.

**5.** Performance improvement (PATCH):

```bash
git commit -m "perf: Optimize database queries."
```
This commit improves performance, so it will trigger a PATCH version increment. For example, if your project is currently at version 
**1.1.1**, this commit would update the version to **1.1.2.**

**6.** Code refactor with a breaking change (MAJOR):
```bash
git commit -m "refactor: Completely rewrite a core module.
BREAKING CHANGE: The module's API has been completely changed."
```
This commit includes a breaking change and will trigger a MAJOR version increment. The version would update to **2.0.0**.

**7.** Code style improvement (No version change):
```bash
git commit -m "style: Fix typos in source files."
```
This commit improves code style but doesn't trigger a version change. It helps in maintaining a consistent codebase.

**8.** Adding missing tests (No version change):
```bash
git commit -m "test: Add unit tests for new features."
```

fix: SK-202 cualquier nombre del p
This commit adds tests but doesn't affect the version. It helps in ensuring code quality through tests.

Following this example workflow, you can see how the version increments based on the nature of the commits and the presence of breaking changes.

## Pull request template

After you have made the Git push, please complete the Pull Request (PR) template file located in the following path within the project: ioet-snack-app-frontend/.github/pull_request_template.md. This template should be filled out on the GitHub page when you confirm the PR in your branch.

- In the section "Describe your changes," provide a brief description of the work related to your ticket.
- In the next section "Issue ticket number and link," include your ticket number and its link, using the following example:
```bash
[SK-#](ticketLink)
Replace "#" with your ticket number
```
- In the section "Type of change," mark the type of your change in the project (considering the standard commits).
- Next, mark the "Checklist" to confirm that your code compiles correctly.
- In the section "Acceptance criteria," copy and paste the acceptance criteria from your ticket.
- In the last section "Notes," you can write any observations about your progress. Additionally, you can include a screenshot as evidence that your code is functioning correctly.

## Pull request naming (to pass the CI)
The pull request naming standard is the next:
```bash
commit scope: SK-# little description
```
- For the commit scope, you can use one of the following:
build, ci, docs, feat, fix, perf, refactor, or test.
- Replace the "#" with your ticket number
- The description should be concise and provide a brief summary of the changes.
  
You can base it on the following examples:
```bash
feat: SK-123 Implement user registration
fix: SK-456 Resolve login validation issue
docs: SK-789 Update installation instructions
```

## Suggestions to make a correct pull request

- Be sure to work in the branch that corresponds to you.
- Don't forget to work on your own.
- If you have no comments in any section, you should not delete the title.
