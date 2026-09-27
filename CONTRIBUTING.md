# Contributing

This repository follows a structured lab-oriented Git workflow.

## Branch Strategy

The master branch contains completed and validated work.

Each lab must be developed on a dedicated branch.

Branch naming convention:

```text
lab/01-osint-tools
lab/02-dns-lookups
lab/03-example-name
```

Do not perform lab development directly on master.

## Standard Workflow

```bash
git switch master
git pull origin master
git switch -c lab/XX-lab-name

# perform and validate the lab

git add labX/
git status
git diff --cached --stat
git commit -m "feat(labX): complete lab description"
git push -u origin lab/XX-lab-name
```

After validation, merge the branch into master.

## Commit Messages

Preferred conventions:

- feat(labX): completed lab work
- docs: documentation changes
- fix: correction to an existing lab
- chore: repository maintenance

## Lab Requirements

Each completed lab should contain:

- a lab README;
- concise technical notes;
- relevant command outputs;
- selected screenshots;
- no unnecessary or sensitive data.

## Root README

The root README.md must be updated whenever a new lab is completed.

The Lab Progress table and the corresponding lab overview should reflect the current repository state.

## Security Requirements

Never commit:

- passwords;
- API keys;
- tokens;
- SSH private keys;
- certificates containing private keys;
- .env files;
- session cookies;
- unnecessary terminal logs containing sensitive information.

Always inspect staged files before committing:

```bash
git status
git diff --cached --stat
git diff --cached --name-only
```
