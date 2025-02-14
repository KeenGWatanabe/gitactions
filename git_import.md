Qn: is there any cli for import instead of logging to github?

If you want to create your own repository from another repository **without cloning or forking**, you can use the **"Import Repository"** feature on GitHub. This allows you to copy the contents of an existing repository into a brand-new repository under your GitHub account, without maintaining a link to the original repository (unlike forking).

---

### **Steps to Import a Repository**

1. **Go to GitHub:**
   - Log in to your GitHub account.

2. **Start the Import Process:**
   - Click the **+** button in the top-right corner of GitHub and select **Import repository**.

3. **Enter the Repository URL:**
   - Provide the URL of the repository you want to copy (e.g., `https://github.com/KeenGWatanabe/RepoName`).

4. **Name Your New Repository:**
   - Choose a name for your new repository.
   - Optionally, add a description and choose visibility (public or private).

5. **Start the Import:**
   - Click **Begin import**. GitHub will copy the entire repository (including all branches, commits, and files) into your new repository.

6. **Wait for the Import to Complete:**
   - The import process may take a few minutes, depending on the size of the repository.

7. **Use Your New Repository:**
   - Once the import is complete, you will have a brand-new repository under your GitHub account. You can clone it, make changes, and push updates as needed.

---

### **Key Differences Between Importing and Forking**
| **Feature**            | **Importing**                              | **Forking**                              |
|-------------------------|--------------------------------------------|------------------------------------------|
| **Link to Original Repo** | No link to the original repository.        | Maintains a link to the original repo.   |
| **Git History**         | Preserves the full commit history.         | Preserves the full commit history.       |
| **Collaboration**       | No connection to the original repo.        | Can submit pull requests to the original repo. |
| **Use Case**            | When you want a completely independent copy. | When you want to contribute to the original repo. |

---

### **Why Use Import Instead of Forking?**
- You want a **completely independent copy** of the repository with no connection to the original.
- You want to **start fresh** without the ability to submit pull requests to the original repository.
- You want to **preserve the commit history** but don’t need the collaboration features of forking.

---

### **Alternative: Manual Copy (Without Git History)**
If you don’t need the commit history and just want the files, you can manually download the repository as a ZIP file and upload it to a new repository:

1. **Download the Repository:**
   - Go to the original repository on GitHub.
   - Click the **Code** button and select **Download ZIP**.

2. **Create a New Repository:**
   - Create a new repository on GitHub.

3. **Upload the Files:**
   - Extract the ZIP file and upload the contents to your new repository using the GitHub web interface or the command line.

---

### **Summary**
- **Import Repository** is the best way to create your own independent copy of another repository while preserving the commit history.
- Use this method when you want a clean break from the original repository and don’t need the collaboration features of forking.