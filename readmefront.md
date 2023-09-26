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
- Jest is a testing framework for fast tests.
- It is compatible with Typescript.

## Installation of dependencies
### Node.js
1. Open the next link https://nodejs.org/es, download the LTS version and install it.
2. Update NPM, the Node package manager, in order to fetch the latest dependencies, use the next command:

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
1. Clone the github repository using the next command:
```bash
git clone https://github.com/ioet/ioet-snack-app-frontend.git
```
2. Create the .env file in the next path: ioet-snack-app-frontend/
3. In the .env file you should create the environmental variables (ask the team the variables).
4. Run the next command in this path: ioet-snack-app-frontend/
```bash
npm run dev
```

## How to run the lint
Use the next command:
```bash
npm run lint
```
If you need correct the linters, use the next command:
```bash
npm run lint:fix
```

## How to run the tests

Use the next command:
```bash
npm run test
```

# How to contribute to the project

## commits standard

## pull request template

## pull request naming (to pass the CI)






## Suggestions to make a correct pull request

- Be sure to work in the branch that corresponds to you.
- Don't forget to work on your own.
- If you have no comments in any section, you should not delete the title.
- 

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
