# Contributing to GitOps Slidev Presentation

Thank you for your interest in contributing! This document provides guidelines for contributing to this project.

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/gitops.git
   cd gitops
   ```
3. **Install dependencies**:
   ```bash
   npm install
   ```
4. **Start the dev server**:
   ```bash
   npm run dev
   ```

## Making Changes

### Before You Start

- Check existing issues and PRs to avoid duplicate work
- For major changes, open an issue first to discuss your proposal
- Keep changes focused and atomic

### Development Workflow

1. **Create a branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes** to `slides.md` or other files

3. **Lint your changes**:
   ```bash
   npm run lint
   ```

4. **Test locally**:
   ```bash
   npm run build
   ```

5. **Commit your changes** with a clear message:
   ```bash
   git commit -m "Add: description of your changes"
   ```

### Commit Message Guidelines

Use clear, descriptive commit messages:
- `Add: new feature or content`
- `Fix: bug fix or correction`
- `Update: changes to existing content`
- `Refactor: code restructuring`
- `Docs: documentation changes`

### Slide Content Guidelines

- Keep slides concise and focused
- Use consistent formatting
- Test that images and links work
- Ensure code examples are correct and properly formatted
- Follow the existing slide structure and style

## Submitting Changes

**Important:** This repository requires all changes to go through Pull Requests. Direct pushes to the `main` branch are not allowed.

1. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Open a Pull Request** on GitHub:
   - Use a clear, descriptive title
   - Reference any related issues
   - Describe what changes you made and why
   - Include screenshots for visual changes

3. **Wait for review**:
   - Address any feedback from maintainers
   - Make requested changes in new commits
   - Keep the PR focused on a single topic
   - Ensure all CI checks pass (linting, build)

## Code Review Process

- All submissions require review before merging
- Maintainers may request changes or improvements
- Once approved, a maintainer will merge your PR

## Reporting Issues

### Bug Reports

Use the bug report template and include:
- Clear description of the issue
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable
- Environment details (browser, OS, etc.)

### Feature Requests

Use the feature request template and include:
- Clear description of the feature
- Use case and benefits
- Possible implementation approach

## Questions?

If you have questions, feel free to:
- Open an issue with the "question" label
- Check existing issues and discussions
- Review the [AGENTS.md](AGENTS.md) file for technical details

## Code of Conduct

This project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
