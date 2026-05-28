# 5. Going Further

Optional, but very useful once the basics feel comfortable.

## Branches — work without breaking things

A **branch** is a parallel copy of your project where you can experiment freely. Your stable work stays on the `main` branch; you create a new branch to try a feature or analysis, and only merge it back into `main` when it works.

```
main      ●───●───●───────────●   <- always stays working
               \             /
feature         ●───●───●───●     <- experiment here, merge back when ready
```

**Why bother:** you can try things without risking your working code, and collaborators can each work on their own branch without stepping on each other.

**GitHub Desktop:**
1. **Current Branch → New Branch**, give it a name (`try-new-filter`).
2. Work and commit as usual.
3. When happy: **Branch → Merge into current branch**, or open a **Pull Request** on GitHub to review and merge it into `main`.

**Terminal:**
```bash
git switch -c try-new-filter   # create and move to a new branch
# ...commit your work...
git switch main                # go back to main
git merge try-new-filter       # bring the changes in
```

## Undoing / rolling back changes

Git's superpower is that almost nothing is ever truly lost. A few common situations:

**"I haven't committed yet and want to throw away my edits to a file."**
- *Desktop:* right-click the file in the Changes list → **Discard changes.**
- *Terminal:* `git restore path/to/file`

**"I want to undo my last commit but keep the edits."**
- *Desktop:* **Branch → Undo last commit.**
- *Terminal:* `git reset --soft HEAD~1`

**"I want to view or recover how a file looked in an earlier commit."**
- *Desktop:* open the **History** tab and click a past commit to see it.
- *Terminal:* `git checkout <commit-id> -- path/to/file`

> [!WARNING]
> Commands like `git reset --hard` permanently discard uncommitted work. If you're unsure, **commit first** (a commit is a safe checkpoint) or stash, then experiment. When in real doubt, ask before running destructive commands.

## Stash — set changes aside temporarily

Sometimes you're half-way through something messy and need a clean project *right now* (e.g. to pull updates). **Stashing** tucks your uncommitted changes away safely, so your working folder returns to the last commit — then you can bring them back later.

**GitHub Desktop:** right-click the current branch → **Stash all changes.** To restore: **Stash → Restore.**

**Terminal:**
```bash
git stash        # hide current changes
git pull         # do your clean operation
git stash pop    # bring your changes back
```

Think of it as a temporary drawer for work-in-progress you're not ready to commit.

> [!NOTE]
> Stash is *not* the same as [staging](03-core-workflow.md): staging picks what goes *into* a commit, while stashing sets changes *aside* instead of committing them.

## Collaborators — working with others

**Invite people (private repo):** on github.com, open your repo → **Settings → Collaborators → Add people** (by username). They get an invite and can then clone, pull and push.

**Clone** = make a local copy of an existing repo:
- *Desktop:* **File → Clone Repository**, pick it from the list.
- *Terminal:* `git clone https://github.com/owner/repo.git`

**Working together without clashing:**
- Always **pull before you start** and **before you push**.
- Use a **branch per person/feature**, then open a **Pull Request** so changes get a quick review before joining `main`.
- If two people changed the same lines, Git asks you to resolve a **merge conflict** — it marks the spots and you choose what to keep. Don't panic; pull often and conflicts stay small.

---

That's it. You now know more Git than most people who use it daily. Revisit the **[core workflow](03-core-workflow.md)** whenever you need a refresher — and keep the **[data rules](04-best-practices.md)** sacred.
