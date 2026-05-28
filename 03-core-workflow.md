# 3. The Core Workflow

This is **the bare minimum**, learn these three actions and you can use Git productively forever. Everything else is a bonus.

The cycle:

```
edit files  →  commit  →  push      (save your work and back it up)
                          pull       (get others' / your other machine's work)
```

## Commit — save a snapshot

A **commit** is a saved snapshot of your project at a point in time, with a short message describing what changed. Commits live on *your computer* until you push them.

A commit happens in **two beats**:

1. **Stage** — pick *which* changes go into this snapshot (tick the files in GitHub Desktop, or `git add` them in the terminal). You don't have to include everything; you can leave some changes for a later commit.
2. **Commit** — save that selection with a message.

> [!NOTE]
> Staging is *not* the same as stashing. **Staging** chooses what goes into your next commit; **stashing** (covered in [Going Further](05-going-further.md)) sets changes *aside* instead of committing them. The names look alike but they do opposite things.

**GitHub Desktop:**
1. Make and save some changes to your files.
2. Open GitHub Desktop — changed files appear on the left, the exact lines that changed on the right.
3. Tick the files you want to include (usually all) — *this is staging*.
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

> [!IMPORTANT]
> **That's the bare minimum.** Commit, push, and pull cover the vast majority of everyday work — you can be productive with just these.

> [!CAUTION]
> Before this becomes a habit, read **[Best Practices](04-best-practices.md)** next — it's short and it's the part that keeps patient data out of GitHub. When you're ready for the optional extras → **[Going Further](05-going-further.md)**.
