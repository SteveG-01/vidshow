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

---

## **🤝 Phase 7: Collaborative Workflow & Pull Requests**

### **12. Working with Others' Code (Forking & Contributing)**

**Step-by-step process to contribute to someone else's project:**

#### **A. Fork and Clone a Repository**
```bash
# 1. Fork the repository on GitHub (click "Fork" button)

# 2. Clone YOUR fork to your computer
git clone https://github.com/YOUR-USERNAME/their-project-name.git
cd their-project-name

# 3. Add the original repository as "upstream" 
git remote add upstream https://github.com/ORIGINAL-OWNER/their-project-name.git

# 4. Verify your remotes
git remote -v
# Should show:
# origin    https://github.com/YOUR-USERNAME/their-project-name.git (fetch)
# origin    https://github.com/YOUR-USERNAME/their-project-name.git (push)
# upstream  https://github.com/ORIGINAL-OWNER/their-project-name.git (fetch)
# upstream  https://github.com/ORIGINAL-OWNER/their-project-name.git (push)
```

#### **B. Create Feature Branch for Your Changes**
```bash
# 1. Make sure you're on main and up-to-date
git checkout main
git pull upstream main

# 2. Create a descriptive feature branch
git checkout -b fix/improve-video-controls
# or
git checkout -b feature/add-mobile-support
# or  
git checkout -b docs/update-readme
```

#### **C. Make Your Changes**
```bash
# 1. Edit the files you need to change
# ... make your improvements ...

# 2. Test thoroughly!
# ... test in browser, run any tests ...

# 3. Commit with clear, descriptive messages
git add .
git commit -m "Fix: Improve video control visibility on mobile devices"

# 4. Make more commits if needed
git add .
git commit -m "Add: Touch-friendly controls for tablet users"
```

#### **D. Push and Create Pull Request**
```bash
# 1. Push your feature branch to YOUR fork
git push origin fix/improve-video-controls

# 2. Go to GitHub and create Pull Request
# - Navigate to the original repository
# - Click "New Pull Request" 
# - Select your branch
# - Write clear title and description
# - Submit the pull request
```

### **13. VS Code Source Control Integration**

#### **Using VS Code's Built-in Git Features:**

**Visual Interface:**
- **Source Control Panel** (Ctrl+Shift+G): See all changes
- **Changes Section**: Files you've modified
- **Staged Changes**: Files ready to commit
- **Git Graph Extensions**: Visual branch history

**Common VS Code Git Actions:**
```
✅ Stage Changes: Click "+" next to file
✅ Unstage Changes: Click "-" next to staged file  
✅ Commit: Type message in box, press Ctrl+Enter
✅ Push: Click "..." → Push
✅ Pull: Click "..." → Pull  
✅ Create Branch: Click branch name → Create new branch
✅ Switch Branch: Click branch name → Select branch
✅ View History: Install "Git History" extension
```

#### **VS Code Pull Request Workflow:**
1. **Install GitHub Pull Requests Extension**
2. **Authenticate with GitHub** 
3. **Create pull requests directly from VS Code**
4. **Review others' pull requests in editor**
5. **Merge pull requests without leaving VS Code**

### **14. Keeping Your Fork Updated**

```bash
# Regular maintenance to stay current with original project

# 1. Fetch latest changes from original repo
git fetch upstream

# 2. Switch to your main branch
git checkout main

# 3. Merge upstream changes into your main
git merge upstream/main

# 4. Push updated main to your fork
git push origin main

# 5. Update your feature branches (optional)
git checkout your-feature-branch
git rebase main  # Apply your changes on top of latest main
```

### **15. Pull Request Best Practices**

#### **Before Submitting:**
```bash
# ✅ Make sure your code works
# ✅ Test thoroughly
# ✅ Update documentation if needed
# ✅ Follow the project's coding style
# ✅ Make sure your branch is up-to-date

# Update your branch with latest main:
git checkout main
git pull upstream main
git checkout your-feature-branch
git rebase main
```

#### **Writing Good Pull Requests:**

**📝 Good PR Title Examples:**
```
✅ "Fix: Video controls not visible on iOS Safari"
✅ "Feature: Add keyboard shortcuts for video navigation" 
✅ "Docs: Update installation instructions for Windows"
✅ "Performance: Reduce video loading time by 50%"
```

**📝 Good PR Description Template:**
```markdown
## What this PR does
Brief description of changes made.

## Why this change is needed  
Explain the problem this solves.

## How to test
1. Step-by-step testing instructions
2. What to look for
3. Any special setup needed

## Screenshots (if UI changes)
Before/after images

## Checklist
- [ ] Code tested locally
- [ ] Documentation updated
- [ ] No breaking changes
- [ ] Follows project style guide
```

### **16. Code Review & Collaboration**

#### **Responding to Review Feedback:**
```bash
# When reviewers request changes:

# 1. Make the requested changes
# ... edit your files ...

# 2. Commit the improvements
git add .
git commit -m "Address review feedback: Improve error handling"

# 3. Push updates (automatically updates the PR)
git push origin your-feature-branch
```

#### **After PR is Merged:**
```bash
# Clean up your local environment

# 1. Switch back to main
git checkout main

# 2. Pull the updated main (includes your merged changes)
git pull upstream main

# 3. Push updated main to your fork
git push origin main

# 4. Delete your feature branch (it's merged now)
git branch -d your-feature-branch
git push origin --delete your-feature-branch
```

### **17. Contributing to Open Source**

#### **Finding Projects to Contribute To:**
- **"Good First Issue"** labels on GitHub
- **"Help Wanted"** tags
- **Documentation improvements**
- **Bug fixes**
- **Translation work**

#### **Open Source Contribution Workflow:**
```bash
# 1. Find interesting project
# 2. Read CONTRIBUTING.md file
# 3. Look for "good first issue" labels
# 4. Fork → Clone → Branch → Code → Test → PR
# 5. Engage respectfully with maintainers
# 6. Be patient with review process
# 7. Learn from feedback
```

---

## **🎯 Complete Collaborative Example**

**Contributing to someone's video player project:**

```bash
# 1. Fork and setup
git clone https://github.com/yourusername/awesome-video-player.git
cd awesome-video-player
git remote add upstream https://github.com/originalowner/awesome-video-player.git

# 2. Create feature branch
git checkout -b feature/add-fullscreen-button
git pull upstream main

# 3. Make improvements
# ... edit HTML/CSS/JS files ...
git add .
git commit -m "Feature: Add fullscreen toggle button with keyboard shortcut"

# 4. Test thoroughly
# ... test in multiple browsers ...
git add .
git commit -m "Fix: Ensure fullscreen works in Safari"

# 5. Push and create PR
git push origin feature/add-fullscreen-button
# Go to GitHub, create Pull Request with clear description

# 6. Respond to feedback
# ... make requested changes ...
git add .
git commit -m "Address review: Use standard fullscreen API"
git push origin feature/add-fullscreen-button

# 7. After merge, cleanup
git checkout main
git pull upstream main
git push origin main
git branch -d feature/add-fullscreen-button
```

---

## **💡 VS Code + Git Pro Tips**

### **Essential VS Code Extensions:**
```
✅ GitLens - Supercharges Git in VS Code
✅ GitHub Pull Requests - PR management
✅ Git Graph - Visual commit history  
✅ Git History - File change timeline
✅ GitHub Copilot - AI code assistance
```

### **VS Code Git Shortcuts:**
```
Ctrl+Shift+G     Open Source Control
Ctrl+Shift+P     Command Palette → Git commands
Ctrl+`           Terminal (for git commands)
F1               Quick Git actions
Alt+Left/Right   Navigate Git file changes
```

### **Workflow Integration:**
1. **Use VS Code's integrated terminal** for Git commands
2. **Use Source Control panel** for staging/committing
3. **Use extensions** for advanced Git features
4. **Use built-in diff viewer** to review changes
5. **Use GitHub integration** for seamless PR workflow

This collaborative workflow opens up the entire world of open source contribution and team development! 🚀