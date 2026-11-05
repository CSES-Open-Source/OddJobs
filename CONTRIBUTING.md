# Contributing to OddJobs

Welcome to OddJobs! This guide covers installation, local development, and how to contribute.

## Contribution Rules

1. You must fork this repo to your account (your origin).
2. Set the upstream of your origin to this master repo.
3. All changes are pushed to your origin.
4. You contribute to the main repo through PRs from your fork.
5. ESLint checks and Prettier style checks must pass before you make a PR.
6. You must test your code with Expo to confirm it does not break the project.

## Workflow

### Why Fork?

Forking protects the main repository by preventing accidental or faulty pushes. Instead of writing directly to the main repo, each engineer works inside their own fork, creates feature branches there, and submits Pull Requests back to the upstream repository. This ensures every change is reviewed, tested, and approved before merging.

### Origin & Upstream

origin → your personal fork on GitHub
upstream → the main Collegiary repository (you must add this)

Your workflow looks like this:
- You push your feature branches to origin (your fork).
- You open a Pull Request from your fork’s branch → upstream main.
- After review and approval, your changes are merged into the main repo.

#### You will never push directly to upstream. All pushes go to origin. Only PRs go to upstream.

## Setup

### Cloning

*Prerequisites: Node.js, Git*

1. Fork the repository: Click Fork in the top-right corner of GitHub, choose your personal GitHub account
2. Clone your fork: 
- `git clone git@github.com:<YOUR HANDLE>/OddJobs.git` (SSH)
- `git clone https://github.com/<YOUR HANDLE>/OddJobs.git` (HTTP)
3. Add the original repo as an upstream remote (if not there):
- `git remote add upstream git@github.com:CSES-Open-Source/OddJobs.git` (SSH)
- `git remote add upstream https://github.com/CSES-Open-Source/OddJobs.git` (HTTP)
4. Check using `git remote -v`

### Node Setup

Install Node dependencies. You may get warnings because React Expo works best with Node 24 and you may have a more recent version. You can ignore this output safely.

```bash
npm install
```

### Environment Variables

Make *OddJobs/mobile/.env* and add this:

```bash
EXPO_PUBLIC_SUPABASE_URL=[YOUR URL]
EXPO_PUBLIC_SUPABASE_PUBLISHABLE_KEY=[YOUR KEY]
```

### Set up Expo

1. Go to the [Expo](https://expo.dev/) website and make an account.
2. Download the **Expo Go** app on your phone, and sign in with that account.
3. Run `npx expo login --no-browser` and sign into the CLI with that account.

### Test Expo

Start the server using:

```bash
npm run start
```

**Mobile:** Scan the QR code and open in Expo Go.

**Web:** Type in `w`.

Confirm that the app works on *both*.

## Contributing

### Branching

Checkout branches any time you start working on an issue or adding a feature.

You can check the branch you are on with `git branch -v`.

1. Create a feature branch:
```bash
    git checkout -b feature/<short-description>
```

#### Update Your Main Branch (Before Starting Branch & After main Repo is merged to)

We will use merge (not rebase) because it avoids rewriting history and is easier for collaboration.
**You must regularly sync your local repository with the main repo to avoid merge conflicts.**

1. Fetch changes from upstream: `git fetch upstream`
2. Merge to your local main branch: `git checkout main` `git merge upstream/main` `git push origin main`

#### Updating while you are working on a Branch

Update your feature branch frequently to avoid large merge conflicts.

1. Fetch changes from upstream: `git fetch upstream`
2. Merge to your local main branch: `git checkout feature/<short-description>` `git merge upstream/main` `git push origin feature/<short-description>`

### Checking

Before committing, you must do the following:

1. Check the app works with `npm run start`.
2. Check lint (code stability) passes with `npm run lint`.
    - If not, run `npm run lint:fix` or fix manually.
3. Check style/format is correct with `npm run format:check`.
    - If not, run `npm run format`.

### Committing and Pushing

In your commit message, preface with one of these tags:

| Label | When to Use |
|-------|-------------|
| `feature` | A new capability or enhancement that does not exist yet. |
| `fix` | Resolved a previous error in the code. |
| `enhancement` | Improvements to existing features, performance, or developer experience. |
| `docs` | Documentation updates, typos, or README/CONTRIBUTING changes. |
| `refactor` | Code cleanup or restructuring without changing behavior. |
| `ci` | Issues related to GitHub Actions, testing, or build pipelines. |
| `chore` | Fixing lint or style. |

Ensure you are in the root directory. Then, save your changes to Github with:

```bash
git add . 
git commit -m "tag: [description]"
git push origin HEAD
```

### Pull Requests

From your fork → main repo, select your branch, target the main repo’s main branch, fill out the PR template.

**If you push to origin, only your local copy is updated. You must open a PR to merge to the official repo.**

#### Feature Branches Only! Do not push directly to main. Your branch will merge after approval.