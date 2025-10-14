# Agent Instructions for Slidev GitOps Project

This document provides context and instructions for AI agents working on this Slidev presentation project.

## Project Overview

This is a Slidev presentation project deployed to GitHub Pages via GitHub Actions. The presentation is available at: https://localgod.github.io/gitops/

## Key Configuration Details

### Base Path Configuration

**Critical:** This project uses a non-root base path for GitHub Pages deployment.

- **Base path:** `/gitops/`
- **Configuration locations:**
  - `vite.config.js`: Sets `base: '/gitops/'`
  - `package.json` build script: Uses `slidev build --base /gitops/`

**Why both?** Slidev requires the `--base` flag during build to generate correct asset paths. The vite.config.js provides additional configuration for the build process.

⚠️ **Do not remove the `--base` flag from the build script** - this will cause 404 errors for all assets on GitHub Pages.

### Development Server in Gitpod

The dev server requires special configuration to work in Gitpod environments:

- **Environment variable:** `__VITE_ADDITIONAL_SERVER_ALLOWED_HOSTS='.gitpod.dev'`
- **Location:** `package.json` dev script
- **Reason:** Vite's host checking blocks Gitpod URLs by default

**Dev script:**
```json
"dev": "__VITE_ADDITIONAL_SERVER_ALLOWED_HOSTS='.gitpod.dev' slidev --remote"
```

The `--remote` flag ensures the server binds to `0.0.0.0` instead of `localhost`.

### Markdown Linting

This project uses `markdownlint-cli` with a permissive configuration for Slidev compatibility.

**Configuration file:** `.markdownlint.json`

**Disabled rules:**
- `MD001`: Heading levels (slides can start at any level)
- `MD003`: Heading styles (setext vs atx)
- `MD013`: Line length
- `MD022`: Headings spacing (conflicts with `---` slide separators)
- `MD024`: Multiple headings with same content
- `MD025`: Multiple top-level headings (each slide can have H1)
- `MD032`: Blank lines around lists
- `MD033`: Inline HTML (Vue components and custom elements)
- `MD034`: Bare URLs
- `MD041`: First line should be H1 (conflicts with frontmatter)
- `MD045`: Alt text for images

**Why so permissive?** Slidev uses:
- YAML frontmatter
- Vue components as HTML elements
- Custom elements (`<v-click>`, `<arrow>`, `<Counter>`, etc.)
- Inline styles and scripts
- Multiple H1s per file (one per slide)
- Slide separators (`---`) that look like horizontal rules

**Scripts:**
- `npm run lint` - Check markdown
- `npm run lint:fix` - Auto-fix issues where possible

## GitHub Actions Workflow

**File:** `.github/workflows/deploy.yml`

**Workflow steps:**
1. Checkout code
2. Setup Node.js (LTS)
3. Install dependencies (`npm ci`)
4. **Lint markdown** (`npm run lint`) - Will fail the build if linting fails
5. Build Slidev (`npm run build`)
6. Configure GitHub Pages
7. Upload artifact from `./dist`
8. Deploy to GitHub Pages

**Triggers:**
- Push to `main` branch
- Manual workflow dispatch

**Permissions:**
- `contents: read`
- `pages: write`
- `id-token: write`

## Project Structure

### Slide Organization

**Important:** This project uses a modular slide structure. Each slide or group of related slides should be in a separate file in the `pages/` directory.

**Main entry point:** `slides.md`
- Contains the frontmatter configuration (theme, title, etc.)
- Contains the cover/title slide
- References all other slides using `src:` directives

**Individual slides:** `pages/*.md`
- Each file contains one or more related slides
- Files are numbered for easy ordering (e.g., `01-what-is-slidev.md`, `02-navigation.md`)
- Referenced from `slides.md` using the `src:` directive

### Slide Reference Syntax

In `slides.md`, reference external slide files like this:

```markdown
---
src: ./pages/01-what-is-slidev.md
---
```

This keeps the main file clean and makes it easy to reorder, add, or remove slides.

## Branch Protection and Pull Request Workflow

**This repository enforces branch protection on the `main` branch.**

### What This Means

- Direct pushes to `main` are blocked
- All changes must go through Pull Requests
- CI checks (linting, build) must pass before merging
- Code review may be required (depending on configuration)

### Workflow for Changes

1. **Create a feature branch:**
   ```bash
   git checkout -b feature/descriptive-name
   ```

2. **Make changes and commit:**
   ```bash
   git add .
   git commit -m "Description of changes"
   ```

3. **Push to the feature branch:**
   ```bash
   git push origin feature/descriptive-name
   ```

4. **Create a Pull Request:**
   ```bash
   gh pr create --title "Title" --body "Description"
   ```

5. **Wait for CI checks and review**

6. **Merge the PR** (via GitHub UI or CLI)

### For Repository Owners

If you need to make quick changes without PR workflow:
1. Temporarily disable branch protection in repository settings
2. Make and push changes
3. Re-enable branch protection

Or use the PR workflow even for your own changes (recommended).

## Common Tasks

### Adding New Slides

**Always create new slides in separate files in the `pages/` directory.**

1. **Create a new file** in `pages/` with a descriptive name:
   ```bash
   # Use numbered prefix for ordering
   pages/15-my-new-slide.md
   ```

2. **Add slide content** to the new file:
   ```markdown
   ---
   # Slide configuration (optional)
   layout: default
   ---

   # Slide Title

   Content here
   ```

3. **Reference the new slide** in `slides.md`:
   ```markdown
   ---
   src: ./pages/15-my-new-slide.md
   ---
   ```

**Why separate files?**
- Easier to manage and navigate
- Better for version control (smaller diffs)
- Allows parallel editing by multiple contributors
- Simplifies reordering slides
- Makes it easier to reuse slides across presentations

### Testing Locally in Gitpod

```bash
npm run dev
```

The server will be available at a Gitpod URL (not localhost). The port will be automatically exposed.

### Building for Production

```bash
npm run build
```

Output will be in `./dist` directory.

### Linting

```bash
# Check for issues
npm run lint

# Auto-fix issues
npm run lint:fix
```

## Troubleshooting

### Assets Return 404 on GitHub Pages

**Symptom:** JavaScript and CSS files return 404 errors when accessing the deployed site.

**Cause:** Missing or incorrect `--base` flag in the build script.

**Solution:** Ensure `package.json` build script includes `--base /gitops/`:
```json
"build": "slidev build --base /gitops/"
```

### Dev Server Shows "Blocked request" Error

**Symptom:** Browser shows "This host is not allowed" error when accessing Gitpod preview URL.

**Cause:** Vite's host checking blocks the Gitpod domain.

**Solution:** Ensure the dev script includes the environment variable:
```json
"dev": "__VITE_ADDITIONAL_SERVER_ALLOWED_HOSTS='.gitpod.dev' slidev --remote"
```

### Linting Fails in CI

**Symptom:** GitHub Actions workflow fails at the "Lint markdown" step.

**Cause:** Markdown doesn't conform to the configured rules.

**Solution:** 
1. Run `npm run lint` locally to see errors
2. Run `npm run lint:fix` to auto-fix where possible
3. Manually fix remaining issues
4. Consider disabling problematic rules in `.markdownlint.json` if they conflict with Slidev syntax

## File Structure

```
my-slidev-project/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md      # Bug report template
│   │   ├── feature_request.md # Feature request template
│   │   └── config.yml         # Issue template config
│   ├── workflows/
│   │   └── deploy.yml         # GitHub Actions workflow
│   └── PULL_REQUEST_TEMPLATE.md # PR template
├── components/                # Vue components
├── pages/                     # Individual slide files (IMPORTANT!)
│   ├── 01-what-is-slidev.md
│   ├── 02-navigation.md
│   ├── 03-table-of-contents.md
│   ├── ...
│   └── 14-learn-more.md
├── snippets/                  # Code snippets
├── .markdownlint.json        # Markdown linting rules
├── AGENTS.md                 # This file
├── CODE_OF_CONDUCT.md        # Code of conduct
├── CONTRIBUTING.md           # Contribution guidelines
├── LICENSE                   # MIT License
├── package.json              # Dependencies and scripts
├── slides.md                 # Main entry point (references pages/)
└── vite.config.js           # Vite configuration
```

**Key directories:**
- `pages/` - **All individual slides go here** (numbered for ordering)
- `components/` - Reusable Vue components
- `snippets/` - External code snippets
- `.github/` - GitHub-specific files (workflows, templates)

## Dependencies

### Production
- `@slidev/cli` - Slidev CLI and core functionality
- `@slidev/theme-default` - Default theme
- `@slidev/theme-seriph` - Seriph theme (currently in use)
- `vue` - Vue.js framework

### Development
- `markdownlint-cli` - Markdown linting tool

## Important Notes for Agents

1. **NEVER commit or push changes unless explicitly asked to do so by the user.** This is critical - always wait for explicit permission before committing.

2. **This repository uses branch protection rules.** Direct pushes to the `main` branch are not allowed. All changes must go through Pull Requests. When the user asks to commit changes, remind them that they'll need to create a PR or temporarily disable branch protection.

3. **For the latest Slidev syntax, always refer to the official guide:** https://sli.dev/guide/syntax - This is the authoritative source for current Slidev markdown features and syntax.

3. **Never remove the `--base` flag** from the build script without updating the deployment configuration.

4. **The vite.config.js base path alone is not sufficient** - Slidev requires the CLI flag.

5. **Always create new slides in separate files** in the `pages/` directory, not in `slides.md`.

6. **Use numbered prefixes** for page files (e.g., `01-`, `02-`) to maintain order.

7. **Reference new slides** in `slides.md` using the `src:` directive.

8. **When modifying linting rules**, test locally first with `npm run lint` before pushing.

9. **The dev server configuration is environment-specific** - the Gitpod configuration won't work in other environments without modification.

10. **GitHub Pages must be configured** to use "GitHub Actions" as the source (not branch-based deployment).

11. **Slide separators (`---`) are not markdown horizontal rules** - they're Slidev syntax for slide boundaries.

12. **Vue components in markdown are intentional** - don't try to "fix" them as HTML errors.

## Resources

- [Slidev Documentation](https://sli.dev/)
- [Slidev Syntax Guide](https://sli.dev/guide/syntax) - **Official reference for latest Slidev markdown syntax**
- [Vite Configuration](https://vitejs.dev/config/)
- [markdownlint Rules](https://github.com/DavidAnson/markdownlint/blob/main/doc/Rules.md)
- [GitHub Actions for Pages](https://github.com/actions/deploy-pages)

## Repository Information

- **Repository:** https://github.com/localgod/gitops
- **Live Site:** https://localgod.github.io/gitops/
- **Owner:** localgod

## Last Updated

2025-10-14 - Initial version documenting project setup and configuration
