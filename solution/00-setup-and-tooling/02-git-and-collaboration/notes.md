# What I Learned: Git & Collaboration

Phase 00: Setup & Tooling · Lesson 02

Source: [Git & Collaboration](../../../phases/00-setup-and-tooling/02-git-and-collaboration/docs/en.md)

Completion: Reported complete by me; recorded on 2026-10-26.
These notes were drafted from the lesson content for my review and submission.
Exercise outputs and quiz scores have not been recorded yet.

## What I learned

I learned how Git tracks changes and how a remote repository supports backup
and collaboration.

- The working directory contains my edits; the staging area selects changes
  for the next commit; a commit records a snapshot in the local repository.
- `git status` shows the current state, `git add` stages changes, and
  `git commit` records them locally.
- `git push` sends local commits to a remote repository. A local commit alone
  does not back up my work on GitHub.
- Branches let me work on experiments separately, and merging brings their
  changes together.
- Forking creates my own hosted copy of a repository; cloning creates a local
  working copy.
- `.gitignore` keeps matching untracked files, such as model checkpoints, out
  of normal staging. It does not stop tracking files already committed.
- `git log --oneline` helps me review the history of a project.

## Practical takeaway

I should inspect my changes, stage the intended files, write a clear commit
message, and push my learning branch to my own remote repository.

Example commands for saving a learning note:

```bash
git status
git add solution/00-setup-and-tooling/02-git-and-collaboration/notes.md
git commit -m "docs(learning): record git and collaboration notes"
git push
```

The push assumes the current branch already has an upstream configured.

## Evidence to add

My fork URL, learning branch, and exercise commit have not been recorded yet.
