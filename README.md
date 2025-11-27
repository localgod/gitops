# GitOps – A Modern Approach to Continuous Delivery

[![Deploy Status](https://github.com/localgod/gitops/actions/workflows/deploy.yml/badge.svg)](https://github.com/localgod/gitops/actions/workflows/deploy.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

A comprehensive presentation on GitOps principles, benefits, and implementation strategies for enterprise architects, DevOps engineers, and platform teams.

**🎯 [View Live Presentation](https://localgod.github.io/gitops/)**

## 📋 Table of Contents

- [About](#about)
- [Presentation Content](#presentation-content)
- [Getting Started](#getting-started)
- [Development](#development)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [Technology Stack](#technology-stack)
- [License](#license)

## About

This presentation explores GitOps as a modern approach to continuous delivery, addressing operational challenges through declarative infrastructure management. It covers:

- Core GitOps principles and definitions
- Problems GitOps solves in modern DevOps workflows
- Comparison with traditional CI/CD approaches
- Implementation workflows and best practices
- Benefits and trade-offs of GitOps adoption

**Target Audience:** Enterprise Architects, DevOps Engineers, Platform Teams

**Presenters:** Johannes H. P. Skov Frandsen and Agata Przybyszewska

## Presentation Content

This slidedeck covers GitOps from background and motivation through practical guidance and lessons learned. Slides are organized into short, focused pages — key topics include:

-- **About the Authors:** Author bio and speaker information (`00-00-about-authors.md`).
-- **Interactive Discussions:** Two short pair-discussion prompts to engage the audience (`01-00-pair-discuss-ci-cd.md`, `02-00-pair-discuss-testing.md`).
-- **Our Journey:** Practical context and historical perspective on CI/CD and IaC tools (`03-01-01-my-journey.md`, `04-01-02-my-journey.md`, `05-01-03-my-journey.md`).
-- **Core Concepts:** What GitOps is and its core principles (`06-02-what-is-gitops.md`).
-- **Problems Solved:** Real operational pain points GitOps addresses (`07-03-problem-gitops-solves.md`).
-- **Comparisons:** GitOps vs traditional CI/CD approaches (`08-04-gitops-vs-traditional-cicd.md`).
-- **Workflow & Day-to-Day:** How GitOps works in practice and the developer/controller feedback loop (`09-05-gitops-workflow.md`).
-- **Code vs Config:** The repository patterns and trade-offs (`10-11-code-vs-config-repo.md`).
-- **Benefits & Trade-offs:** Practical pros and cons to consider when adopting GitOps (`11-06-benefits-of-gitops.md`).
-- **Tools & Patterns:** Overview of popular GitOps tools (`12-08-gitops-tools.md`).
-- **Security & Governance:** Secrets handling, SCM as a control plane, and access implications (`13-09-security-considerations.md`).
-- **Migration & Anti-Patterns:** Practical migration strategy and common pitfalls to avoid (`14-10-migration-strategy.md`, `15-12-anti-patterns.md`).
-- **Measuring Success:** Metrics and indicators to track adoption impact (`16-13-measuring-success.md`).
-- **Summary:** Key takeaways and recommendations (`17-07-summary.md`).

Each slide is intentionally concise; to add or reorder slides, create separate files under the `pages/` directory and reference them from `slides.md` (see `CONTRIBUTING.md` for authoring and contribution guidelines).

## Getting Started

### Prerequisites

- Node.js (LTS version recommended)
- npm or pnpm

### Installation

```bash
# Clone the repository
git clone https://github.com/localgod/gitops.git
cd gitops

# Install dependencies
npm install
```

### Running Locally

```bash
# Start the development server
npm run dev
```

The presentation will be available at the URL shown in the terminal (not localhost in Gitpod environments).

## Development

### Project Structure

```
.
├── pages/              # Individual slide files
│   ├── 02-what-is-gitops.md
│   ├── 03-problem-gitops-solves.md
│   └── ...
├── slides.md           # Main entry point and configuration
├── components/         # Vue components (if needed)
├── public/            # Static assets
└── .github/
    └── workflows/
        └── deploy.yml  # Automated deployment
```

### Adding New Slides

All slide authoring and file-organization guidelines live in `CONTRIBUTING.md`.
See `CONTRIBUTING.md` for guidance on adding new slides, naming, and review process.

### Available Commands

```bash
# Development
npm run dev          # Start dev server

# Building
npm run build        # Build for production

# Linting
npm run lint         # Check markdown
npm run lint:fix     # Auto-fix markdown issues

# Export
npm run export       # Export to PDF
```

### Markdown Linting

This project uses markdownlint with a permissive configuration for Slidev compatibility. Run `npm run lint` before committing changes.

## Deployment

The presentation is automatically deployed to GitHub Pages via GitHub Actions when Pull Requests are merged to the `main` branch.

**Deployment URL:** https://localgod.github.io/gitops/

### Branch Protection

This repository uses branch protection. See `CONTRIBUTING.md` for full details on branch rules and the pull request process.

### Manual Deployment

To trigger a manual deployment:

1. Go to [Actions](https://github.com/localgod/gitops/actions)
2. Select "Deploy Slidev to GitHub Pages"
3. Click "Run workflow"

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](./CONTRIBUTING.md) for details on:

- How to submit changes
- Coding standards
- Commit message conventions
- Pull request process

Please also read our [Code of Conduct](./CODE_OF_CONDUCT.md) before contributing.

See `CONTRIBUTING.md` for step-by-step contribution and pull request guidance.

## Technology Stack

- **[Slidev](https://sli.dev/)** - Presentation framework for developers
- **[Vue 3](https://vuejs.org/)** - Progressive JavaScript framework
- **[Vite](https://vitejs.dev/)** - Next-generation frontend tooling
- **[UnoCSS](https://unocss.dev/)** - Instant on-demand atomic CSS engine
- **[markdownlint](https://github.com/DavidAnson/markdownlint)** - Markdown linting

## Documentation

- [AGENTS.md](./AGENTS.md) - Technical documentation for AI agents and developers
- [CONTRIBUTING.md](./CONTRIBUTING.md) - Contribution guidelines
- [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md) - Community guidelines

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Acknowledgments

- Built with [Slidev](https://sli.dev/) by Anthony Fu
- Theme: [Seriph](https://github.com/slidevjs/themes/tree/main/packages/theme-seriph)

---

**Questions or Issues?** Please [open an issue](https://github.com/localgod/gitops/issues/new/choose) or check our [discussions](https://github.com/localgod/gitops/discussions).
