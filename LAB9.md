# Lab 9 execution record

## Clone and local hotfix

```sh
git clone https://github.com/monggulie/branch-test.git branch-new
cd branch-new
# Append "hotfix my solution" to edition.txt.
git add edition.txt
git commit -m "hotfix my solution"
```

An independent remote commit appended `Hotfix team's solution` to the same location.

## Divergence and conflict

```sh
git push origin main
# Rejected: main -> main (fetch first)
git fetch origin
git merge origin/main
# CONFLICT (content): Merge conflict in edition.txt
```

Observed conflict:

```text
<<<<<<< HEAD
hotfix my solution
=======
Hotfix team's solution
>>>>>>> origin/main
```

Resolution: keep `Hotfix team's solution` and remove all conflict markers.

```sh
git add edition.txt
git commit -m "Resolved conflict"
# Append "New function added" to edition.txt.
git add edition.txt
git commit -m "new function added"
git push origin main
```

## Remote upgrade and synchronization

An independent remote `Upgraded` commit appended `Team upgraded`.

```sh
git pull --ff-only origin main
# Fast-forward: 1 file changed, 1 insertion(+)
```

`git fetch` updates the remote-tracking refs without changing the working tree. A subsequent `git merge origin/main` integrates those commits. `git pull` fetches and then integrates; `--ff-only` requires a fast-forward.

## Final expected edition.txt

```text
first edition
second edition
third edition
issue resolved
Hotfix team's solution
New function added
Team upgraded
```

## Inspect the history

```sh
git log --oneline --graph --all
git show --format=fuller --no-patch HEAD
git status --short
git rev-parse HEAD origin/main
```

The `Resolved conflict` commit has two parents, preserving the local and remote hotfix histories. The initial feature branch is retained as `codex/testing`.
