# Bear's Commit Workflow

A lightweight GitHub Actions toolkit inspired by Conventional Commits.

Bear's Commit Workflow helps keep commits consistent, pull requests organized, and repository labels structured through reusable commit templates and automated GitHub Actions workflows.

## Features

### Commit Template

A reusable commit template inspired by Conventional Commits.

**Supported types:**

| Type | Description |
|---|---|
| `feat` | New features |
| `fix` | Bug fixes |
| `refactor` | Code structure improvements |
| `style` | Formatting changes without logic changes |
| `chore` | Tooling, dependencies, and maintenance |
| `docs` | Documentation changes |
| `test` | Adding or updating tests |
| `perf` | Performance improvements |
| `ci` | CI/CD changes |
| `build` | Build system changes |

### Setup Labels Workflow

Automatically creates and updates GitHub labels from `.github/config/labels.json`.

Labels are configured with predefined names, colors, and descriptions. The configuration also includes metadata such as emojis and priorities for use by other workflows.

### PR Bot

Validates pull request titles against the supported Conventional Commit types.

The bot can:

- Validate pull request title formats.
- Support scoped commit types, such as `feat(auth):`.
- Apply the matching type label.
- Reject invalid pull request formats.
- Prevent duplicate type labels.

**Valid examples:**

```text
feat: add login system
fix(api): resolve timeout issue
refactor(auth): simplify JWT validation
```

**Invalid example:**

```text
updated login stuff
```

### PR Summary

Automatically generates and updates a pull request summary based on its commit messages.

The workflow can:

- Collect valid commit messages from the pull request.
- Sort commits by configured type priority.
- Generate a `Commits Included` section with the configured emojis.
- Use the highest-priority valid commit as the pull request title.
- Apply the corresponding type label.

### PR Size

Automatically calculates the size of a pull request using the total number of lines added and deleted.

The workflow applies one size label and replaces the previous size label when the pull request changes.

| Label | Changed lines |
|---|---:|
| `size/xs` | 0–9 |
| `size/s` | 10–49 |
| `size/m` | 50–199 |
| `size/l` | 200–499 |
| `size/xl` | 500+ |

Size labels make it easier to identify small, manageable pull requests and larger changes that may need additional review.

## Example Commits

```text
feat: add user authentication system
fix: resolve crash when submitting empty form
refactor: extract API logic into separate service
style: format code with prettier
chore: update dependencies
docs: add installation instructions
test: add unit tests
perf: optimize image loading
ci: add GitHub Actions workflow
build: configure Vite build output
```

## Setup

### Local Repository

Configure Git to use the commit template:

```bash
git config commit.template commit-template/commit-template.txt
```

### Global Setup

Configure a global commit template:

```bash
git config --global commit.template ~/.gitmessage.txt
```

Copy the contents of `commit-template/commit-template.txt` into `~/.gitmessage.txt`.

### GitHub Actions

The workflows are located in `.github/workflows/`:

| Workflow | Purpose |
|---|---|
| `setup-labels.yml` | Creates and updates repository labels |
| `pr-bot.yml` | Validates PR titles and applies type labels |
| `pr-summary.yml` | Generates a PR title and commit summary |
| `pr-size.yml` | Applies a size label based on changed lines |
| `daily_commit.yml` | Runs the configured daily commit workflow |

The workflows use `.github/config/labels.json` to share label configuration.

**Requirements:**

- GitHub Actions enabled for the repository.
- Appropriate workflow permissions.
- A valid `.github/config/labels.json` configuration.
- A commit template configured locally if you want Git to use it automatically.

## Configuration

Edit `.github/config/labels.json` to customize supported commit types, label colors, descriptions, emojis, priorities, and pull request size thresholds.

Keep the configuration compatible with the workflows that read it.

---

Built to make GitHub workflows cleaner, more consistent, and easier to maintain.