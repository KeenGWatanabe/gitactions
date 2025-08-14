Absolutely, Roger — you can push changes from your `dev` branch to `main` using the command line in GitHub Codespaces, just like in any local Git environment. Here's a clean, step-by-step way to do it:

### 🧠 Option 1: Merge `dev` into `main` and push
If you want to **merge** the changes from `dev` into `main`, do this:

```bash
# Switch to main branch
git checkout main

# Pull latest changes from remote main (optional but recommended)
git pull origin main

# Merge dev into main
git merge dev

# Push updated main to GitHub
git push origin main
```

This keeps the commit history intact and is ideal for feature integration.

---

### 🔁 Option 2: Force push dev over main (⚠️ destructive)
If you want to **overwrite** `main` with the exact state of `dev` (e.g., replacing it entirely), you can do:

```bash
git push origin dev:main
```

Or, if you’re absolutely sure and want to force it:

```bash
git push origin dev:main --force
```

⚠️ This rewrites history on `main`, so use it only if you're confident no one else is relying on the current `main`.

---

Let me know if you want to set up branch protection rules or CI triggers for `main` after the push. I can help you lock it down for production safety.
