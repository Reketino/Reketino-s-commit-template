# 🔧 Bear's Commit Template

A simple and clean commit message template inspired by conventional commits.

Keeping commits structured makes your project easier to read, review, and maintain.

## 📦 Commit Types

- Type:	Description
- feat:	New feature
- fix:	Bug fix
- refactor:  Code change that improves structure
- style: Formatting, no logic changes
- chore: Tooling, dependencies, cleanup
- docs:	 Documentation only
- test:	 Adding or updating tests
- perf:	 Performance improvements
- ci:	 CI/CD changes
- build: Build system changes

## ✍️ Example Commits

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

## ⚙️ Setup

### Local
- git config commit.template .commit-template.txt

### Global
- git config --global commit.template ~/.commit-template.txt

## 💡 Why use this?
Cleaner commit history
Easier code reviews
Better collaboration
More professional workflow