# 1. Setup

You need three things: a GitHub account, the Git tool, and (recommended) the GitHub Desktop app.

## Step 1 — Create a GitHub account

1. Go to [github.com](https://github.com) and sign up.
2. Use an email you'll keep access to. For work projects, check whether your institution has an organization or recommends a specific email.
3. Pick a clear username — colleagues will see it.

> [!TIP]
> GitHub accounts are free, and free accounts include **unlimited private repositories**. You do not need to pay to keep your work private.

## Step 2 — Install GitHub Desktop (recommended for beginners)

GitHub Desktop is a free app that lets you do everything with buttons instead of typing commands.

1. Download it from [desktop.github.com](https://desktop.github.com).
2. Install and open it.
3. Sign in with the GitHub account you just made (it prompts you on first launch, or **File → Options → Accounts**).

Installing GitHub Desktop also installs Git for you — so if you go this route, you're done.

## Step 3 (optional) — The command line

If you'd rather use the terminal, you need Git installed:

- **Mac:** open Terminal and type `git --version`. If it's missing, macOS offers to install it, or run `xcode-select --install`.
- **Windows:** download from [git-scm.com](https://git-scm.com/download/win).
- **Linux:** `sudo apt install git` (Debian/Ubuntu) or your distro's equivalent.

Then tell Git who you are (this name appears on every change you save):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

> [!NOTE]
> Use the **same email** as your GitHub account, so your changes are linked to your profile.

---

Once you can open GitHub Desktop and see your account, you're ready. Next: **[Create a Repository](02-create-a-repository.md)**.

> [!IMPORTANT]
> Before you put any *real* work into a repo, read **[Best Practices](04-best-practices.md)** — especially the rules about never committing patient data.
