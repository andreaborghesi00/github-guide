# 2. Create a Repository

A **repository** ("repo") is just a project folder that Git tracks. It holds your code, its history, and a record of every change.

> [!IMPORTANT]
> This guide assumes **one project = one folder.** All the code for a given project lives in a single directory, and that directory becomes the repository. Keep different projects in different folders.

> [!CAUTION]
> **Do not turn a broad, catch-all folder into a repository** — not your **Desktop**, your **Documents**, or your whole home folder. Git would then track *everything* inside it: unrelated projects, personal files, and possibly data you'd never want online. Always point Git at the **single folder for one project** and nothing wider.

## Public vs Private — decide first

When you create a repo you choose its visibility:

|  | **Private** 🔒 | **Public** 🌍 |
|---|---|---|
| Who can see it | Only you and people you invite | Anyone on the internet |
| Good for | Work projects, anything touching medical data, unpublished research | Open-source tools, teaching material, published code |
| Our default | **Use this** when unsure | Only after a deliberate check |

> [!CAUTION]
> For anything connected to the hospital, patients, or unpublished research, choose **Private**. You can always make a repo public later; you cannot un-expose data that was visible while it was public.

> [!NOTE]
> Private does **not** mean safe-to-store-data. The [no-data rule](04-best-practices.md) applies to private repos too — "private" only limits *who can see the code*.

## Create one with GitHub Desktop

1. **File → New Repository.**
2. **Name** it (e.g. `ecg-analysis`). Keep it short, no spaces.
3. Pick a **local path** — where the folder lives on your computer.
4. Tick **"Initialize this repository with a README."**
5. Set **Git ignore** to a template (e.g. *Python*) — this creates a starter `.gitignore` for you. You can edit it afterwards using the [example](.gitignore) in this guide.
6. Click **Create Repository.**
7. Click **Publish repository** (top bar) to put it on GitHub. **This is where you tick "Keep this code private."**

### Already have a folder of code?

Most of the time your project already exists as a folder. Then instead of *New Repository*:

1. **File → Add Local Repository.**
2. Choose the **folder for that one project** — *not* your Desktop or Documents (see the warning above).
3. GitHub Desktop offers to **create a repository** in it; accept, then **Publish repository** and tick **"Keep this code private."**

> [!TIP]
> Add a `.gitignore` (see [Best Practices](04-best-practices.md)) *before* you publish, so any data already sitting in that folder is excluded from the very first commit.

## Create one in the terminal

```bash
# inside the folder you want to turn into a repo
git init
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
```

Then create an empty repo on github.com (the **+** menu → **New repository**, choose **Private**) and connect it:

```bash
git remote add origin https://github.com/your-username/your-repo.git
git branch -M main
git push -u origin main
```

> [!TIP]
> The Desktop app is much easier for this first-time setup. Once the repo exists, day-to-day work is the same either way → **[The Core Workflow](03-core-workflow.md)**.
