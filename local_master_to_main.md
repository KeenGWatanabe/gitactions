Got it! Here are the steps to rename your local repo branch from `master` to `main`, and then update the remote repo accordingly:

### 1. Rename Local Branch
1. **Check out to the `master` branch:**
   ```bash
   git checkout master
   ```
2. **Rename the branch to `main`:**
   ```bash
   git branch -m master main
   ```

### 2. Update the Remote Repository
1. **Delete the old `master` branch in the remote repository:**
   ```bash
   git push origin --delete master
   ```
2. **Push the `main` branch to the remote repository:**
   ```bash
   git push origin main
   ```
3. **Set the remote `main` as the default branch:**
   ```bash
   git push --set-upstream origin main
   ```

### 3. Update Branch References (if needed)
1. **In case there are any references to the old `master` branch in your project, update them to `main`.**

### 4. Update Default Branch Settings (Optional)
1. **Go to your repository settings on GitHub, GitLab, or your preferred platform, and change the default branch to `main`.**

### 5. Cleanup
1. **Prune remote-tracking branches:**
   ```bash
   git fetch --prune
   ```

That’s it! Your local and remote repos should now be aligned with the branch name `main` instead of `master`. If there’s anything else you need, just let me know!