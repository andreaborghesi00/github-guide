# Getting Started with GitHub — A Guide for the Team

A short, practical introduction to Git and GitHub for people who write code as part of their work (technical medicine, biomedical engineering, data & AI) but were never formally taught version control.

You don't need a computer-science background. The goal is to get you from *"my code lives in a folder on my laptop"* to *"my code is versioned, backed up, and shareable"* — without bad habits, and **without ever leaking patient data.**

---

## Why bother? (the 2-minute version)

Right now a project often looks like this:

```
analysis_final.py
analysis_final_v2.py
analysis_final_v2_REALLYfinal.py
analysis_USE_THIS_ONE.py
```

We've all been there. Version control fixes this. With Git + GitHub you get:

- **A complete history**: every saved version is recoverable. You can see what changed, when, and why, and roll back to any earlier state.
- **A backup off your laptop**: if your machine dies, your work doesn't.
- **A way to collaborate**: several people work on the same project without emailing zip files around.
- **A single source of truth**: no more guessing which file is the latest.

Two terms people mix up:

- **Git** is the tool that tracks changes (runs on your computer).
- **GitHub** is the website that stores your project online and lets you share it.

Both are built for **code and small text files, not large data or model weights**, which belong in proper storage. More on this in [Best Practices](04-best-practices.md).

---

## Read this first

Because we work with medical data and AI, one rule matters more than everything else in this guide:

> [!CAUTION]
> **Never put patient data, or any real medical data, into a Git repository.**
> Once data is pushed to GitHub it is extremely hard to remove fully, and on a public repo it may already have been copied. Read **[Best Practices](04-best-practices.md)** before you put any real work into a repo.

> [!NOTE]
> This guide assumes **one project = one folder**: all the code for a given project lives in a single directory on your computer, and *that folder* becomes the repository. If your project is scattered across several places, gather it into one folder first.

---

## How to read this guide

These first four pages are the **essentials**, read them in order and you'll be productive:

1. **[Setup](01-setup.md)**: install the tools and create your account.
2. **[Create a Repository](02-create-a-repository.md)**: make your first repo; public vs private.
3. **[The Core Workflow](03-core-workflow.md)**: commit, push, pull. This is all you need day to day.
4. **[Best Practices](04-best-practices.md)**: what's good, what's a hard no (data!), and `.gitignore`. **Don't skip this**, it's the part that keeps medical data safe.

When you're comfortable and want more:

5. **[Going Further](05-going-further.md)**: branches, undoing changes, stash, and collaborators.

> [!NOTE]
> Every step is shown **two ways**: with **GitHub Desktop** (a free point-and-click app, easiest to start with) and the **terminal / command line** for those who prefer it or need it later. Use whichever you like; they do the same thing.
