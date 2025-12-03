Here's a comprehensive guide to free up space on your 500GB SSD while keeping your coding environment intact:

## **🎯 Quick Wins (Easy & Safe)**

### 1. **Docker Cleanup**
```bash
# Remove unused Docker resources
docker system prune -a

# Remove all stopped containers
docker container prune

# Remove unused images
docker image prune

# Remove unused volumes (BE CAREFUL - contains data)
docker volume prune
```

### 2. **Git Repository Optimization**
```bash
# Clean up local repo caches (run in each repo)
git gc --aggressive --prune=now

# Remove old git branches that were merged
git branch --merged | grep -v "\*" | xargs git branch -d
```

### 3. **VS Code Cache & Extensions**
- Clear VS Code cache: `%APPDATA%\Code\Cache` (Windows) or `~/Library/Application Support/Code/Cache` (Mac)
- Delete unused VS Code extensions
- Clear `~/.vscode` or `%USERPROFILE%\.vscode` of old configs

## **📊 First: Analyze What's Using Space**

### Windows:
```powershell
# PowerShell as Admin
WinDirStat  # GUI tool
# or
tree /f /a > tree.txt  # Check large folders
```

### Mac/Linux:
```bash
# Show largest directories
du -hs * | sort -rh | head -20

# Visual tool
ncdu  # Install with brew/apt
# or
brew install ncdu
sudo ncdu /  # Run with sudo for system-wide
```

## **🧹 Deep Clean by Category**

### **Virtual Machine Space Recovery:**
1. **Compact VM disks** (especially VirtualBox/Vmware)
2. **Remove snapshots** - these can double VM size
3. **Clean VM caches** inside the OS
4. Consider moving **less-used VMs to external drive**

### **Node.js Projects:**
```bash
# Remove node_modules from old projects
find ~/projects -name "node_modules" -type d -exec du -sh {} \; | sort -hr

# Optionally delete (careful!)
find ~/projects -name "node_modules" -type d -exec rm -rf {} \;
```

### **Python Environments:**
```bash
# Clear pip cache
pip cache purge
# or
rm -rf ~/.cache/pip

# Remove old virtual environments
# Check ~/venv, ~/.virtualenvs, project/.venv directories
```

## **🗂️ Smart File Management**

### **1. Move Large Files Elsewhere:**
- Backup old projects to cloud (GitHub/GitLab free repos)
- Archive completed projects to external drive
- Use **Git LFS** for large binary files instead of storing in repo

### **2. Clear System Caches:**
- **Windows:** Disk Cleanup (cleanmgr.exe), Temp files (`%TEMP%`)
- **Mac:** `~/Library/Caches`, `~/Library/Logs`
- **Linux:** `/var/cache`, `~/.cache`

### **3. Log Files:**
```bash
# Check large log files
find /var/log -type f -size +100M  # Linux
find ~/Library/Logs -type f -size +50M  # Mac
```

## **🔧 Tools to Help**

### **Windows:**
- **WizTree** (faster than WinDirStat)
- **SpaceSniffer**
- **Storage Sense** (Settings → System → Storage)

### **Mac:**
- **DaisyDisk** ($10 but excellent)
- **OmniDiskSweeper** (free)
- **GrandPerspective** (free)

### **Linux:**
- **Baobab** (Disk Usage Analyzer)
- **Filelight** (KDE)
- **ncdu** (terminal-based)

## **🚀 Prevention & Optimization**

### **1. Configure Docker:**
```json
// Add to ~/.docker/daemon.json
{
  "storage-driver": "overlay2",
  "storage-opts": [
    "overlay2.size=20G"  # Limit Docker storage
  ]
}
```

### **2. VS Code Settings:**
```json
// settings.json
{
  "files.maxMemoryForLargeFilesMB": 4096,
  "git.autofetch": false,  // Reduces git cache
  "update.mode": "manual"  // Avoid download cache
}
```

### **3. Git Strategy:**
- Clone with `--depth=1` for large repos you just need to read
- Use `git sparse-checkout` for monorepos
- Store only active projects locally

### **4. Use Cloud/External Storage:**
- **Google Drive/Dropbox** for documentation
- **External SSD** for VM backups/archives
- **GitHub/GitLab** for code history (instead of local)

## **📝 My Recommended Cleanup Order:**

1. **Run system cleanup tools** (Storage Sense/Disk Cleanup)
2. **Clear Docker** (~5-10GB typically)
3. **Remove old VM snapshots** (huge savings!)
4. **Archive completed projects** to external drive
5. **Delete `node_modules`** from inactive projects
6. **Clear system caches/logs**
7. **Uninstall unused apps** via Settings → Apps

## **⚠️ Important Caution:**
- **Never delete system files** you don't understand
- **Backup before deleting** from virtual machines
- **Keep at least 15-20% SSD free** for performance/longevity
- Some Docker containers may have **important data** in volumes

**Quick check:** Run this first to see your biggest space hogs:
```bash
# On Mac/Linux/WSL
sudo du -ah / 2>/dev/null | sort -rh | head -50
```

Start with the Docker cleanup and system caches - those are usually the lowest-hanging fruit for developers!
