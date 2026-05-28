# 3. The Core Workflow

This is **the bare minimum**, learn these three actions and you can use Git productively forever. Everything else is a bonus.

The cycle:

```
edit files  →  commit  →  push      (save your work and back it up)
                          pull       (get others' / your other machine's work)
```

## Commit — save a snapshot

A **commit** is a saved snapshot of your project at a point in time, with a short message describing what changed. Commits live on *your computer* until you push them.

**GitHub Desktop:**
1. Make and save some changes to your files.
2. Open GitHub Desktop — changed files appear on the left, the exact lines that changed on the right.
3. Tick the files you want to include (usually all).
4. Type a **summary** message at the bottom left ("Add bandpass filter").
5. Click **Commit to main.**

**Terminal:**
```bash
git add .                          # stage all changed files
git commit -m "Add bandpass filter"
```

> [!TIP]
> A good message finishes the sentence *"This commit will…"* — e.g. *"…fix the off-by-one in the windowing."* Commit one logical change at a time.

## Push — send commits to GitHub

A **push** uploads your commits to GitHub. This is what backs them up and makes them visible to collaborators.

**GitHub Desktop:** click **Push origin** (top bar).

**Terminal:**
```bash
git push
```

## Pull — get the latest changes

A **pull** downloads commits made by others (or by you on another computer) and merges them into your copy. **Pull before you start working** so you're up to date.

**GitHub Desktop:** click **Fetch origin**, then **Pull origin** if there's anything to pull.

**Terminal:**
```bash
git pull
```

> [!NOTE]
> Typical day: **pull → work → commit → push.** Repeat.

---

## Bonus: stash — set changes aside temporarily

Sometimes you're half-way through something messy and need a clean project *right now* (e.g. to pull updates). **Stashing** tucks your uncommitted changes away safely, so your working folder returns to the last commit — then you can bring them back later.

**GitHub Desktop:** right-click the current branch → **Stash all changes.** To restore: **Stash → Restore.**

**Terminal:**
```bash
git stash        # hide current changes
git pull         # do your clean operation
git stash pop    # bring your changes back
```

Think of it as a temporary drawer for work-in-progress you're not ready to commit.

---

> [!IMPORTANT]
> **That's the bare minimum.** Commit, push, pull (+ the occasional stash) cover the vast majority of everyday work — you can be productive with just these.

> [!CAUTION]
> Before this becomes a habit, read **[Best Practices](04-best-practices.md)** next — it's short and it's the part that keeps patient data out of GitHub. When you're ready for the optional extras → **[Going Further](05-going-further.md)**.
