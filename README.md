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

## Presentation Content

The presentation consists of 7 slides:

1. **Title Slide** - Introduction and audience context
2. **What is GitOps?** - Definition and core principles
3. **Problem GitOps Solves** - Operational challenges and solutions
4. **GitOps vs Traditional CI/CD** - Comparative analysis
5. **GitOps Workflow Overview** - Implementation workflow
6. **Benefits of GitOps** - Pros and cons analysis
7. **Summary & Key Takeaways** - Conclusion and main points

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

All slides should be created as separate files in the `pages/` directory:

1. Create a new file: `pages/08-new-slide.md`
2. Add your content using Slidev markdown syntax
3. Reference it in `slides.md`:
   ```markdown
   ---
   src: ./pages/08-new-slide.md
   ---
   ```

For detailed guidelines, see [AGENTS.md](./AGENTS.md).

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

The presentation is automatically deployed to GitHub Pages via GitHub Actions on every push to the `main` branch.

**Deployment URL:** https://localgod.github.io/gitops/

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

### Quick Contribution Guide

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes in separate page files
4. Run linting (`npm run lint`)
5. Commit your changes (see [CONTRIBUTING.md](./CONTRIBUTING.md) for commit conventions)
6. Push to your branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

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
