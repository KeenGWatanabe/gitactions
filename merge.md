Qn: git commit -m "merge"
[master e820743] merge
is it merge or not?

The command `git commit -m "merge"` creates a new commit with the message "merge". However, this does not necessarily mean that a merge has actually occurred. It simply records a snapshot of the current state of the repository with the commit message "merge".

To determine if a merge actually happened, you would need to check the commit history or the context in which the commit was made. Here are a few ways to check:

1. **Check the commit history:**
   Use `git log` to see the commit history. If a merge occurred, you should see a merge commit with two parent commits.

   ```sh
   git log --oneline --graph
   ```

   A merge commit typically looks something like this:

   ```
   *   e820743 (HEAD -> master) merge
   |\  
   | * abc1234 Some other branch commit
   * | def5678 Some master branch commit
   |/  
   * 1234567 Previous commit
   ```

2. **Check the status before committing:**
   If you ran `git merge` before committing, then it is likely that a merge occurred. You can check the status before committing using:

   ```sh
   git status
   ```

   If you were in the process of resolving merge conflicts, `git status` would have indicated that.

3. **Check the parents of the commit:**
   You can also check the parents of the commit to see if it is a merge commit:

   ```sh
   git show --pretty=raw e820743
   ```

   Look for the `parent` lines. If there are two parents, it is a merge commit.

4. **Check the reflog:**
   The reflog can show you the history of what happened in your repository:

   ```sh
   git reflog
   ```

   This can help you see if a merge operation was performed.

In summary, the commit message "merge" does not confirm that a merge occurred. You need to inspect the commit history or the context to determine if a merge actually took place.