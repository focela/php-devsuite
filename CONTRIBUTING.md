# Contributing to PHP DevSuite

We appreciate your interest in contributing to **PHP DevSuite**, an all-in-one Docker-based PHP development suite for **Laravel, WordPress, Magento, and more**.  
Your contributions help improve the project, making it more efficient and developer-friendly for everyone!

To ensure a smooth contribution process, please follow the guidelines below.

## **1. How to Contribute**
### **Reporting Issues & Feature Requests**
If you find a bug or want to propose a new feature, please [open an issue][open-issue].  
Make sure to include:
- A **clear description** of the issue or feature request.
- Steps to reproduce the issue (if applicable).
- Expected vs. actual behavior.
- Any relevant logs, screenshots, or code snippets.

### **Submitting Code Changes**
Before submitting changes, you need to sign the [Focela Contributor License Agreement (CLA)][cla].  
A bot will remind you to sign the CLA when you open a pull request.

## **2. Setup Instructions**
To contribute, first **fork the repository**, then clone your fork:

```bash
git clone git@github.com:your_github_username/php-devsuite.git
cd php-devsuite
git remote add upstream https://github.com/focela/php-devsuite.git
git fetch upstream
```

## **3. Making Changes**
### **Create a New Branch**
Before making any changes, create a new branch:

```bash
git checkout main
git fetch upstream
git rebase upstream/main
git checkout -b feature/new-cool-feature
```

### **Make Your Changes**
- Follow the project's **coding style guide** (PSR-12 for PHP).
- Write tests for any new functionality.
- Ensure that your code does not break existing functionality.
- Write **clear and descriptive commit messages** ([commit guidelines][commit-message]).

### **Push and Open a Pull Request**
Once you're happy with your changes, push them to your fork:

```bash
git push origin feature/new-cool-feature
```

Then, open a **pull request (PR)** on GitHub.

## **4. Code Review Process**
After submitting a PR:
1. A **maintainer** will review your changes within a few business days.
2. They may request changes or suggest improvements.
3. If your changes meet all requirements, a maintainer will merge your PR.

To **increase the chances of your PR being merged**:
- Write **tests** for new features.
- Use **clear commit messages**.
- Ensure **backward compatibility** is maintained.


## **5. Contributor Expectations**
- Be respectful in all interactions ([Code of Conduct][code-of-conduct]).
- Follow best practices for **security** and **performance**.
- Keep contributions **focused** and **well-documented**.

Thank you for helping make PHP DevSuite better! 🚀

[open-issue]: https://github.com/focela/php-devsuite/issues/new
[cla]: https://cla-assistant.io/focela/php-devsuite
[commit-message]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[code-of-conduct]: CODE_OF_CONDUCT.md  
