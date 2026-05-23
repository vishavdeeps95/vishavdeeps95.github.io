# Git Workflow Cheat Sheet

A friendly, plain-English guide to the git commands you'll use most often. Run
these in a terminal from inside your project folder.

---

## 1. One-time setup

Do these once when starting a brand-new project.

```bash
git init
```
Turns the current folder into a git project so it can start tracking changes.

```bash
git add .
```
Picks up every file in the folder so they're ready to be saved.

```bash
git commit -m "First commit"
```
Saves a snapshot of those files with a short note describing it.

```bash
git remote add origin https://github.com/your-username/your-repo.git
```
Connects your local project to its home on GitHub (replace the URL with yours).

```bash
git push -u origin main
```
Uploads your snapshot to GitHub for the first time. The `-u` tells git to
remember this connection so future pushes are simpler.

---

## 2. The everyday loop

Repeat this every time you finish an editing session.

```bash
git add .
```
Gathers up everything you changed since the last save.

```bash
git commit -m "Describe what you changed"
```
Saves a snapshot with a short message — write it so future-you understands.

```bash
git push
```
Sends your latest snapshots up to GitHub.

---

## 3. Seeing history

```bash
git log
```
Shows a list of every saved snapshot, newest first, with the messages you wrote.
Press `q` to exit.

```bash
git diff
```
Shows the exact lines you've changed since your last save — useful before you
commit.

---

## 4. How to undo

### Discard uncommitted changes to a file
```bash
git checkout -- filename.txt
```
Throws away your edits to that file and brings back the last saved version.

### Undo the last commit but keep the work
```bash
git reset --soft HEAD~1
```
Rewinds the last commit, but all your changes stay in place so you can redo it.

### Revert a bad commit that's already pushed
```bash
git revert <commit-hash>
```
Creates a new commit that undoes the bad one — safe to use after pushing
because it doesn't rewrite history. Get the hash from `git log`.

### Go back to view an older version
```bash
git checkout <commit-hash>
```
Lets you look at the project exactly as it was at that snapshot. Run
`git checkout main` when you're done to come back to the present.

### Recover a file you deleted by accident
```bash
git checkout HEAD -- filename.txt
```
Brings the file back from the last saved snapshot.

---

## 5. Recreate the project on another computer

```bash
git clone https://github.com/your-username/your-repo.git
```
Downloads the whole project — files, history, and all — into a new folder on
the other computer. Then `cd` into that folder and you're ready to work.
