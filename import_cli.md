Qn: is there any cli for import instead of logging to github?


Yes, you can use the **GitHub CLI (`gh`)** to import a repository directly from the command line without logging into the GitHub website. The GitHub CLI provides a command called `gh repo create` with the `--import` flag, which allows you to import a repository from a remote URL.

---

### **Steps to Import a Repository Using GitHub CLI**

1. **Install GitHub CLI:**
   If you don’t already have the GitHub CLI installed, you can download and install it from [GitHub CLI's official page](https://cli.github.com/).

   - On **Linux**:
     ```bash
     sudo apt install gh
     ```
   - On **macOS**:
     ```bash
     brew install gh
     ```
   - On **Windows**:
     Use the installer from the GitHub CLI page.

2. **Authenticate GitHub CLI:**
   Authenticate the GitHub CLI with your GitHub account:
   ```bash
   gh auth login
   ```
   Follow the prompts to log in.

3. **Import the Repository:**
   Use the `gh repo create` command with the `--import` flag to import a repository:
   ```bash
   gh repo create <new-repo-name> --import --source=<source-repo-url>
   ```

   - Replace `<new-repo-name>` with the name you want for your new repository.
   - Replace `<source-repo-url>` with the URL of the repository you want to import.

   Example:
   ```bash
   gh repo create MyNewRepo --import --source=https://github.com/KeenGWatanabe/RepoName
   ```

4. **Wait for the Import to Complete:**
   The import process will start, and you’ll see a progress indicator. Once the import is complete, the new repository will be available under your GitHub account.

---

### **Key Notes About `gh repo create --import`**
- The imported repository will **preserve the full commit history**.
- The new repository will be **independent** of the original repository (unlike forking, which maintains a link to the original).
- You can specify the repository visibility (`--public`, `--private`, or `--internal`) during creation:
  ```bash
  gh repo create MyNewRepo --import --source=https://github.com/KeenGWatanabe/RepoName --private
  ```

---

### **Alternative: Manual Import Using Git and GitHub CLI**
If you prefer more control over the process, you can manually clone the repository, create a new repository, and push the contents:

1. **Clone the Source Repository:**
   ```bash
   git clone https://github.com/KeenGWatanabe/RepoName
   cd RepoName
   ```

2. **Create a New Repository on GitHub:**
   Use the GitHub CLI to create a new repository:
   ```bash
   gh repo create MyNewRepo --private --push --source=.
   ```

   - `--private`: Makes the new repository private (use `--public` for a public repository).
   - `--push`: Pushes the local repository to the new remote repository.

3. **Verify the Import:**
   Check your GitHub account to confirm that the new repository has been created and contains the imported content.

---

### **Summary**
- The GitHub CLI (`gh`) provides a convenient way to import a repository directly from the command line using `gh repo create --import`.
- This method is ideal for automating repository imports or working entirely from the command line.
- If you need more control, you can manually clone the repository, create a new one, and push the contents using the GitHub CLI.