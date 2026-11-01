# Lecture 9: Remote Branch and Collaboration

Practicing Git branching, merging, remote collaboration, and conflict resolution.

Repository: https://github.com/monggulie/branch-test

## Completed workflow

1. Created the initial three editions, resolved an issue on `main`, and merged the separate `codex/testing` feature branch.
2. Pushed the local repository to a new public GitHub repository, then cloned it into a separate working copy.
3. Committed `hotfix my solution` locally while independently committing `Hotfix team's solution` on GitHub's remote `main` through the GitHub API.
4. Attempted a push and received the expected `fetch first` rejection.
5. Ran `git fetch origin`, followed by `git merge origin/main`, which produced a content conflict in `edition.txt`.
6. Removed the conflict markers, retained the team's hotfix as shown in the lecture, and committed `Resolved conflict`.
7. Added `New function added`, committed, and pushed to GitHub.
8. Created the independent remote `Upgraded` commit adding `Team upgraded`, then ran `git pull --ff-only origin main` to synchronize both working copies.

The remote edits used the GitHub API in place of the website editor so the commit author and committer could explicitly use a no-reply email. The collaboration exercise uses one account and two working copies; it does not imply participation by another person.

## Files

- `edition.txt`: the lecture's final synchronized text.
- `new_feature.txt`: the feature introduced on the separate branch.
- `LAB9.md`: commands, observed results, and verification notes.

## Privacy

Only the practice text and documentation are included. No personal documents, lecture files, transcripts, credentials, student IDs, or private contact details are included. All commits use the public GitHub handle and a GitHub no-reply email. An allowlist in `.gitignore` helps prevent accidental additions.
