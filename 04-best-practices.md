# 4. Best Practices (the rules that keep data safe)

Git is powerful, which also means it can permanently record mistakes. A few habits keep you safe and make your repositories useful to others.

## The big no-nos

> [!CAUTION]
> **Never commit patient data or any real medical data.**
> No CSVs of patient records, no DICOM/MRI images of real patients, no exported database tables, no spreadsheets with identifiers — nothing that contains or could re-identify a person.
>
> Once data is pushed it is uploaded to a server outside your control. Even if you delete it afterwards, it remains in the project history, and on a public repo it may already have been copied or indexed. This can be a data-protection breach (GDPR / HIPAA and your institution's rules).

Also never commit:

- **Credentials & secrets** — passwords, API keys, tokens, database connection strings, `.env` files. Anyone who reads the repo can use them.
- **Large data files & model weights** — Git is built for *code* (text), not gigabytes of data. Big files bloat the repo and slow everyone down. Use proper data storage instead.
- **Anything you can't legally redistribute** — licensed datasets, third-party data under agreement.

> [!IMPORTANT]
> Rule of thumb: **a repository holds code and small text files — the *recipe*, not the *ingredients*.** Code that *reads* data from a separate location is fine; the data itself stays out.

## Good habits

- **Commit small and often**, with a clear message ("Add baseline filtering to ECG pipeline" beats "stuff" or "update").
- **Keep data and code separate.** Point your code at a data folder *outside* the repo, or at a shared drive.
- **Write a `README`** so future-you and colleagues know what the project does and how to run it.
- **Don't commit generated junk** — outputs, caches, `__pycache__`, huge plots. These can be regenerated.
- **Think before going public** (see [public vs private](02-create-a-repository.md)). When in doubt, **private**.

## `.gitignore` — your safety net

A `.gitignore` is a plain text file you put in your project. It lists files and folders Git should **completely ignore** — never track, never commit, never push. This is the main tool that stops data and secrets from leaking by accident.

You list patterns, one per line:

```gitignore
# Data — never commit
data/
*.csv
*.dcm          # DICOM images
*.nii          # NIfTI / medical imaging
*.xlsx

# Secrets
.env
*.key
credentials.json

# Python junk
__pycache__/
*.pyc
.ipynb_checkpoints/

# Model weights / large files
*.h5
*.ckpt
*.pt
```

> [!TIP]
> Create the `.gitignore` **before your first commit**, and add your data folder to it immediately. Then anything you drop in `data/` is invisible to Git — you can't push it by accident.
>
> A ready-to-use example [`.gitignore`](.gitignore) is included in this repo. Copy it into your project and adjust as needed.

> [!WARNING]
> `.gitignore` only protects files that **aren't already tracked**. If you accidentally committed data, ignoring it afterwards is *not* enough — the data is still in the history. If that happens, stop and ask for help removing it properly, and treat any leaked credentials as compromised (rotate them immediately).

---

When you're ready for the optional extras → **[Going Further](05-going-further.md)**.
