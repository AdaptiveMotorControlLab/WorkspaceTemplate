# Development Guide

## Table of Contents
- [Code Review Best Practices](#code-review-best-practices)
- [Issue Management](#issue-management)
- [Collaborative Coding Guidelines](#collaborative-coding-guidelines)
- [Code Formatting](#code-formatting)

## Code Review Best Practices

### For Reviewers

1. **Be Constructive and Respectful**
   - Focus on the code, not the person 🔐
   - Provide clear, actionable feedback 🚧
   - Explain the "why" behind your suggestions
   - Use a positive and encouraging tone 💜

2. **Review Checklist**
   - Code follows [project style guidelines](https://github.com/AdaptiveMotorControlLab/WorkspaceTemplate/blob/mwm/dev-guide/docs/StyleGuide.md)
   - No obvious bugs or security issues
   - **Tests** are included and pass
   - Documentation is updated
   - Performance considerations are addressed
   - Error handling is appropriate

3. **Timely Reviews**
   - Respond to review requests within 24 hours
   - If you can't review immediately, communicate your timeline
   - Don't let PRs sit idle for extended periods

4. **Focus Areas**
   - Functionality: Does it work as intended?
   - Maintainability: Is the code clean and well-structured?
   - Testability: Is it easy to test?
   - Security: Are there any security concerns?
   - Performance: Are there any performance implications?

### For Authors

1. **Before Submitting**
   - Make a branch and adhere to the naming convention: `yourname/issue`
   - Self-review your changes
   - Run all tests locally
   - Run the `pre-commit` checks & formatting!
   - Update documentation!
   - Keep changes focused and manageable -- "MVP-R" what is the minimally viable PR -- would you want to review it?
   - Follow the project's commit message conventions

2. **PR Description**
   - Clear title describing the change
   - Detailed description of changes
   - Link to related issues
   - Screenshots for UI changes
   - Testing instructions

## Issue Management

### Creating Issues

1. **Issue Template**
   - Use the provided issue templates
   - Fill out all required sections
   - Be specific and detailed

2. **Issue Types**
   - Bug: Describe the current behavior and expected behavior
   - Feature: Explain the use case and benefits
   - Enhancement: Detail the improvement
   - Documentation: Specify what needs to be updated

3. **Issue Content**
   - Clear, descriptive title
   - Detailed description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Environment details
   - Screenshots/videos when relevant

### Managing Issues

1. **Labels**
   - Use appropriate labels (bug, enhancement, etc.)
   - Priority labels when necessary
   - Component/area labels

2. **Assignments**
   - Assign issues to specific team members
   - Set realistic deadlines
   - Update status regularly

3. **Communication**
   - Keep discussions in the issue thread
   - Tag relevant team members
   - Update issue status promptly

## Collaborative Coding Guidelines

Each project is different, so please check project-specific guidelines.
However, below is a guide for collaborative projects in general.
I recommend the following system for within-lab projects that have different levels of maintainers & builders.

### Who is developing?

1. **Organize weekly dev meetings**
   - Review the current issues, PRs, and major milestones.
   - Self-assessment: are you blocking anyone? If so, work to fix that.
   - No one person is the gate-keeper for the project: work together
2. **Get a review assignment system in place**
   - 🟥 Make a flag for **major dev/changes**: all users of the code should agree and sign off (git reviews), and this includes the PI.
   - 🟧 Make a flag for **user-needs**: this is needed to stop a block -- it might not be perfect, so make an issue to revisit later. 1 sign off from another user, and go! 🚀
   - 🟩 Make a flag for **minor change**: not breaking, can be changed later, 1 sign off okay

### Git Workflow

1. **Branching Strategy**
   - Use feature branches for new work
   - Branch naming convention: `name/issue-number-description`
     - Example: `john/123-add-login-feature`
     - Example: `sarah/456-fix-navigation-bug`
   - Keep branches up to date with main
   - Delete branches after merging

2. **Commits**
   - Write clear, descriptive commit messages
   - Keep commits focused and atomic
   - Reference issue numbers in commits
   - Follow conventional commits format

3. **Pull Requests**
   - Keep PRs small and focused
   - Update PR description as changes are made
   - Request reviews from appropriate team members
   - Address review comments promptly

### Communication

1. **Team Communication**
   - Use appropriate channels for different purposes - use basecamp campfire and github issues/PRs
   - Be clear and concise
   - Document important decisions!!
   - Share knowledge and learnings

2. **Code Documentation**
   - Document complex logic in the code with comments!
   - Keep README up to date
   - Add inline comments when necessary
   - Document API changes

3. **Knowledge Sharing**
   - Share learnings with the team
   - Document common patterns
   - Create and maintain team documentation
   - Regular team sync-ups, organize them!

### Development Environment

1. **Setup**
   - Document environment setup
   - Use consistent development tools
   - Share configuration/docker files
   - Maintain development dependencies

2. **Local Development**
   - Follow our development guidelines
   - Use consistent formatting tools
   - Run tests before committing (see `pre-commits`)
   - Keep dependencies updated

3. **Code Quality**
   - Use our suggeested linters and formatters
   - Follow our style guides


## Code Formatting

### General Formatting Rules

We use the Google Style Guide: https://google.github.io/styleguide/

1. **Indentation**
   - Use 2 spaces for indentation
   - No tabs
   - Maximum indentation level: 4 levels
   - Align with opening delimiter

2. **Line Length**
   - Maximum line length: 100 characters
   - Break long lines at logical points
   - Indent continuation lines by 4 spaces
   - Break after operators, not before

3. **Whitespace**
   - No trailing whitespace
   - One blank line between functions/classes
   - Two blank lines between major sections
   - No multiple consecutive blank lines
   - Spaces around operators
   - No spaces inside parentheses
   - Spaces after commas and semicolons

4. **Naming Conventions**
   - Variables: `lower_snake_case`
   - Functions: `lower_snake_case`
   - Classes: `PascalCase`
   - onstants: `UPPER_SNAKE_CASE`
   - Files: `lower_snake_case.py`
   - Private members: `_single_leading_underscore`
   - Modules/Packages: `lower_snake_case`
   - Interfaces: `PascalCase` (same as classes, no special prefix)

5. **Comments**
   - Use clear, concise comments
   - Comment complex logic
   - Keep comments up to date
   - Remove commented-out code

6. **Imports/Exports**
   - Group imports in the following order:
     1. Third-party imports
     2. Project imports
   - Sort imports by `isort` within the groups
   - Use named exports
   - Avoid default exports
   - One import per line

7. **Code Organization**
   - One class/component per file
   - Group related functionality
   - Keep files focused and manageable
   - Follow the project's file structure
   - RECOMMENDED: Maximum file length: 1000 lines
   - RECOMMENDED: Maximum function length: 50 lines


### Automated Formatting

1. **Pre-commit Hooks**
   - Run formatters before commit
   - Run linters before commit
   - Check for common issues
   - Ensure consistent formatting
   - Block commits with formatting errors

2. **CI/CD Integration**
   - Run formatting checks in pipeline
   - Fail builds on formatting errors
   - Generate formatting reports
   - Enforce style guide compliance
   - Use Google's style guide linters

### Google Style Guide Compliance

1. **General Principles**
   - Be consistent with existing code
   - Be consistent with Google's style guide
   - Use Google's official linters
   - Follow language-specific style guides
   - Document any style guide exceptions

2. **Code Review Requirements**
   - Check style guide compliance
   - Verify formatting is correct
   - Ensure consistent naming
   - Validate documentation
   - Review for best practices

3. **Style Guide Resources**
   - [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)

---

Remember: These guidelines are living documents. Feel free to suggest improvements and updates as the team evolves and learns.
