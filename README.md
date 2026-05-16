# 🔧 Bear's Commit Workflow

A lightweight GitHub workflow toolkit inspired by conventional commits.

This project focuses on improving commit consistency, pull request structure, and repository organization through commit templates, GitHub labels, and automated PR validation.

Keeping workflows structured makes projects easier to maintain, review, and scale over time.

---

# 🎯 Purpose of the Project

The goal of this project is not just to standardize commit messages, but to build a cleaner and more automated development workflow around GitHub.

The toolkit helps:

* enforce consistent PR titles
* automate label management
* improve commit readability
* reduce manual repository maintenance
* create a cleaner developer workflow

---

# 📦 Included Features

## 🔹 Commit Template

A reusable commit template inspired by conventional commits.

### Supported Types

* feat → new feature
* fix → bug fix
* refactor → code structure improvements
* style → formatting, no logic changes
* chore → tooling, dependencies, cleanup
* docs → documentation only
* test → adding or updating tests
* perf → performance improvements
* ci → CI/CD changes
* build → build system changes

---

## 🔹 Setup Labels Workflow

Automatically creates and updates GitHub labels with predefined:

* names
* colors
* descriptions

This ensures consistent issue and PR labeling across repositories.

### Included Labels

* feat
* fix
* refactor
* style
* chore
* docs
* test
* perf
* ci
* build

---

## 🔹 PR Bot

A GitHub Actions powered PR validation bot.

The bot automatically:

* validates pull request titles
* supports scoped commits (`feat(auth):`)
* applies matching labels automatically
* prevents duplicate labels
* fails invalid PR formats

### Valid Examples

```txt
feat: add login system

fix(api): resolve timeout issue

refactor(auth): simplify JWT validation
```

### Invalid Example

```txt
updated login stuff
```

---

# ✍️ Example Commits

```txt
feat: add user authentication system

fix: resolve crash when submitting empty form

refactor: extract API logic into separate service

style: format code with prettier

chore: update dependencies to latest versions

docs: add installation instructions to README

test: add unit tests for login service

perf: optimize image loading with lazy loading

ci: add GitHub Actions workflow for testing

build: configure Vite build output settings
```

---

# ⚙️ Setup

## Local Repository

```bash
git config commit.template commit-template/commit-template.txt
```

## Global Setup

```bash
git config --global commit.template ~/.gitmessage.txt
```

Copy the template content into:

```txt
~/.gitmessage.txt
```

---

# 💡 Why use this?

* Cleaner commit history
* Better pull request structure
* Easier code reviews
* Automated GitHub workflow management
* More professional collaboration flow
* Consistent repository organization

---

Built to make GitHub workflows cleaner, more automated, and easier to maintain.
