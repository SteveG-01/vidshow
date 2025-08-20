# **Complete Git Workflow - From Project Creation to Branch Management**

## **🚀 Phase 1: Project Setup**

### **1. Create Your Project Directory**
```bash
mkdir my-new-project
cd my-new-project
```

### **2. Create Your Initial Files**
```bash
# Create your main files
touch index.html
touch style.css
touch script.js
# Or create any files you need for your project
```

### **3. Initialize Git Repository**
```bash
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

---

## **📝 Phase 2: Initial Commit**

### **4. Stage and Commit Your Initial Work**
```bash
# Check what files exist
git status

# Add all files to staging
git add .

# Make your first commit
git commit -m "Initial commit: Project setup"
```

### **5. Create Your Branch Structure**
```bash
# Create and switch to development branch
git checkout -b development

# Verify your branches
git branch -v
```

---

## **🔄 Phase 3: Daily Development Workflow**

### **6. Making Changes (Recommended Pattern)**

**Always work on `development` branch:**
```bash
# Make sure you're on development
git checkout development

# Check current status
git status

# Edit your files (make your changes)
# ... work on your code ...

# Stage your changes
git add .

# Commit with descriptive message
git commit -m "Add new feature: full-screen video player"
```

### **7. Multiple Commits During Development**
```bash
# Make some changes
git add .
git commit -m "Fix: Remove video controls completely"

# Make more changes  
git add .
git commit -m "Feature: Add infinite loop functionality"

# Make final changes
git add .
git commit -m "Style: Improve full-screen layout"
```

---

## **🎯 Phase 4: Production Deployment**

### **8. When Ready for "Production"**
```bash
# Switch to main branch
git checkout main

# Merge all your development work
git merge development

# Check that everything merged correctly
git log --oneline --graph
```

---

## **📊 Phase 5: Viewing Your Work**

### **9. Essential Commands to Check Your Progress**

**See current status:**
```bash
git status          # What's changed right now
git branch          # What branch am I on?
git log --oneline   # History of commits
```

**Compare changes:**
```bash
git diff                    # See current uncommitted changes
git diff main development   # Compare branches
git show HEAD              # See last commit details
```

**Switch between versions:**
```bash
git checkout main          # Go to production version
git checkout development   # Go to development version
git checkout [commit-hash] # Go to specific commit (read-only)
```

---

## **🔧 Phase 6: Advanced Workflow (Optional)**

### **10. Feature Branches (For Larger Projects)**
```bash
# Create specific feature branch from development
git checkout development
git checkout -b feature/video-controls

# Work on feature...
git add .
git commit -m "Add video control functionality"

# Merge back to development when done
git checkout development
git merge feature/video-controls

# Delete feature branch (cleanup)
git branch -d feature/video-controls
```

### **11. Backup to Remote (GitHub/GitLab)**
```bash
# Add remote repository
git remote add origin https://github.com/yourusername/your-repo.git

# Push main branch
git push -u origin main

# Push development branch  
git push -u origin development
```

---

## **🎨 Complete Example Workflow**

Let's say you want to create a new website project:

```bash
# 1. Setup
mkdir awesome-website
cd awesome-website

# 2. Create files
touch index.html style.css script.js

# 3. Initialize Git
git init
git config user.name "John Doe"
git config user.email "john@example.com"

# 4. Initial commit
git add .
git commit -m "Initial commit: Basic website structure"

# 5. Create development branch
git checkout -b development

# 6. Make changes (edit your files)
# ... edit index.html, add content ...

# 7. Commit changes
git add .
git commit -m "Add homepage content and navigation"

# 8. Continue development
# ... edit style.css, add styling ...
git add .
git commit -m "Add CSS styling and responsive design"

# 9. More development
# ... edit script.js, add interactivity ...
git add .
git commit -m "Add JavaScript animations and interactions"

# 10. Ready for production
git checkout main
git merge development

# 11. Check your work
git log --oneline --graph
```

---

## **🚨 Emergency Commands (When Things Go Wrong)**

### **Undo Changes:**
```bash
# Undo uncommitted changes
git checkout -- filename.html    # Undo changes to specific file
git checkout .                   # Undo all uncommitted changes

# Undo last commit (but keep changes)
git reset --soft HEAD~1

# See what happened
git reflog                       # Shows everything you've done
```

### **Branch Management:**
```bash
# List all branches
git branch -a

# Delete a branch
git branch -d branch-name

# Rename current branch
git branch -m new-branch-name
```

---

## **💡 Best Practices Summary**

### **✅ DO:**
- **Work on `development` branch** for all changes
- **Commit often** with descriptive messages
- **Use `main` branch** only for stable, tested code
- **Check `git status`** frequently
- **Test your code** before merging to main

### **❌ DON'T:**
- **Don't work directly on `main`** branch
- **Don't make huge commits** - break them into smaller pieces
- **Don't use vague commit messages** like "fix stuff"
- **Don't merge untested code** into main

### **📝 Commit Message Examples:**
```bash
# Good commit messages:
"Add: Full-screen video player with autoplay"
"Fix: Remove video controls that were briefly visible"
"Update: Change video URL to Pocatello promotional video"
"Style: Improve responsive layout for mobile devices"

# Bad commit messages:
"updates"
"fix"
"changes"
"work in progress"
```

**This workflow gives you:**
- ✅ **Safe experimentation** on development branch
- ✅ **Stable production** version on main branch  
- ✅ **Complete history** of all your changes
- ✅ **Easy rollback** if something breaks
- ✅ **Professional development** practices

You can now confidently create projects, track changes, and manage different versions of your work!

---

## **📚 Quick Reference Commands**

### **Most Used Daily Commands:**
```bash
git status                    # Check current status
git add .                     # Stage all changes
git commit -m "message"       # Save changes
git checkout development      # Switch to dev branch
git checkout main             # Switch to main branch
git log --oneline            # See commit history
```

### **Branch Commands:**
```bash
git branch                   # List branches
git checkout -b new-branch   # Create and switch to new branch
git merge branch-name        # Merge branch into current branch
git branch -d branch-name    # Delete branch
```

### **Helpful Commands:**
```bash
git diff                     # See current changes
git show HEAD               # See last commit
git reflog                  # See all actions taken
```