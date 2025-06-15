Renaming branches in Git (both locally and remotely) involves a few steps. Here's how to do it:

---

### **1. Rename a Local Branch**
#### **If you're NOT on the branch you want to rename:**
```sh
git branch -m <old-name> <new-name>
```
Example:
```sh
git branch -m feature/old-name feature/new-name
```

#### **If you're currently on the branch you want to rename:**
```sh
git branch -m <new-name>
```
Example:
```sh
git checkout feature/old-name
git branch -m feature/new-name
```

---

### **2. Delete the Old Remote Branch & Push the New One**
Since Git doesn’t directly support renaming remote branches, you must:
1. **Delete the old remote branch**  
2. **Push the new branch**  
3. **Reset upstream tracking** (if needed)

#### **Step-by-Step:**
```sh
git push origin --delete <old-name>          # Delete old remote branch
git push origin <new-name>                  # Push new branch
git branch -u origin/<new-name> <new-name>  # Set upstream (optional)
```

Example:
```sh
git push origin --delete feature/old-name
git push origin feature/new-name
git branch -u origin/feature/new-name
```

---

### **3. Update Local Tracking (If Needed)**
If your local branch was tracking the old remote branch, update it:
```sh
git branch --unset-upstream <new-name>      # Remove old tracking
git branch -u origin/<new-name>             # Link to new remote
```

---

### **4. Verify Changes**
Check remote branches:
```sh
git fetch -p
git branch -a
```

---

### **Important Notes:**
✅ **Collaborators must update their local repos:**  
   - They should run:
     ```sh
     git fetch -p
     git checkout <new-name>
     ```
   - If they have the old branch locally, they should delete it:
     ```sh
     git branch -D <old-name>
     ```

🚫 **Avoid renaming published branches if others are using them** (it can cause confusion).

---

### **Summary**
1. Rename locally: `git branch -m <old> <new>`  
2. Delete old remote: `git push origin --delete <old>`  
3. Push new branch: `git push origin <new>`  
4. Update tracking: `git branch -u origin/<new>`  

Would you like a script to automate this? 😊