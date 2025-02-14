Let’s break down your questions and clarify the differences between cloning, forking, and GitHub Pages.

---

### **1. Cloning a Repository**
When you run:

```bash
git clone https://github.com/KeenGWatanabe/RepoName
```

or

```bash
git clone https://github.com/KeenGWatanabe/RepoName NewRepoName
```

- **What Happens?**
  - Git creates a **local copy** of the remote repository on your machine.
  - The remote repository (origin) is still linked to the original repository (`https://github.com/KeenGWatanabe/RepoName`).
  - If you specify a new name (`NewRepoName`), the cloned repository will be saved in a folder with that name instead of the default repository name (`RepoName`).

- **Does It Create Your Own Repo?**
  - No, cloning does not create a new repository on GitHub. It only creates a local copy of the existing repository.
  - You do not have write access to the original repository unless you are a collaborator.

- **Is It a Fork?**
  - No, cloning is not the same as forking. Forking creates a **copy of the repository under your GitHub account**, while cloning simply downloads the repository to your local machine.

---

### **2. Forking a Repository**
To create your own copy of a repository on GitHub (a fork), you must use the **Fork** button on the GitHub website. This creates a new repository under your GitHub account that is linked to the original repository.

- **Steps to Fork:**
  1. Go to the repository on GitHub (e.g., `https://github.com/KeenGWatanabe/RepoName`).
  2. Click the **Fork** button in the top-right corner.
  3. This creates a new repository under your GitHub account (e.g., `https://github.com/YourUsername/RepoName`).

- **Cloning a Fork:**
  After forking, you can clone your forked repository to your local machine:

  ```bash
  git clone https://github.com/YourUsername/RepoName
  ```

  Now you have a local copy of your forked repository, and you can push changes to your fork.

---

### **3. Cloning vs. Forking**
| **Action** | **Cloning** | **Forking** |
|------------|-------------|-------------|
| **Where It Happens** | Local machine | GitHub |
| **Creates a New Repo** | No (local copy only) | Yes (on your GitHub account) |
| **Write Access** | Only if you are a collaborator | Yes (to your fork) |
| **Linked to Original Repo** | Yes (as `origin`) | Yes (as `upstream`) |

---

### **4. GitHub Pages**
GitHub Pages is a feature that allows you to host a website directly from a GitHub repository. For example, if you have a repository named `keengwatanabe.github.io`, you can host a website at `https://keengwatanabe.github.io`.

- **How to Set Up GitHub Pages:**
  1. Create a repository named `username.github.io` (e.g., `keengwatanabe.github.io`).
  2. Add your HTML/CSS/JavaScript files to the repository.
  3. Go to the repository settings on GitHub, scroll down to the **Pages** section, and enable GitHub Pages.
  4. Your site will be published at `https://keengwatanabe.github.io`.

- **Example:**
  If you have an `index.html` file in your repository, it will be accessible at:
  ```
  https://keengwatanabe.github.io/index.html
  ```

---

### **5. Cloning with a Different Name**
When you clone a repository with a different name:

```bash
git clone https://github.com/KeenGWatanabe/RepoName NewRepoName
```

- The repository is cloned into a folder named `NewRepoName` instead of `RepoName`.
- This is useful if you want to avoid naming conflicts or organize your local workspace.

---

### **Summary**
- **Cloning** downloads a repository to your local machine but does not create a new repository on GitHub.
- **Forking** creates a copy of the repository under your GitHub account.
- **GitHub Pages** allows you to host a website from a GitHub repository.

If you want to contribute to the original repository, you should **fork** it first, then clone your fork. If you just want to work locally, cloning is sufficient. For hosting a website, use GitHub Pages with a repository named `username.github.io`.