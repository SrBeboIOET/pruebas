# Guide to Using Commits and Semantic Versioning (SemVer)

Version control and proper commit practices are crucial for managing software projects effectively. Combining commits with Semantic Versioning (SemVer) helps maintain a clear history of changes and enables developers to communicate the impact of updates clearly. This guide will walk you through the process of using commits and SemVer together in your development workflow.

## Version Control System

First, ensure that you have set up a version control system (VCS) such as Git for your project. Git allows you to track changes, collaborate with others, and manage your codebase efficiently.

## Semantic Versioning (SemVer)

As a quick reminder, [Semantic Versioning (SemVer)](https://semver.org/) consists of three parts: **MAJOR**, **MINOR**, and **PATCH**. Increment these versions based on the type of changes:

1. **MAJOR:** For backward-incompatible changes.
2. **MINOR:** For backward-compatible feature additions.
3. **PATCH:** For backward-compatible bug fixes.

## Commit Guidelines

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

## Version Incrementation

Use the commit messages to determine the appropriate version increment:

1. **MAJOR:** If any commit message includes a **BREAKING CHANGE**, increment the MAJOR version.
2. **MINOR:** If there are commits with new features (**feat** scope) but no **BREAKING CHANGE**, increment the MINOR version.
3. **PATCH:** If there are only bug fixes (**fix** scope), performance improvements (**perf** scope), or other non-breaking changes, increment the PATCH version.

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

Following this example workflow, you can see how the version increments based on the nature of the commits and the presence of breaking changes.
