## 3. The Daily Git Workflow

We don't just push code directly into the final product. We use a step-by-step process to ensure everything is reviewed and safe. 

### Step 1: Create a New Branch
The **main branch** is where all the final, working code lives. When you want to add a new feature or fix a bug, you must create a safe, isolated copy of the code called a **branch**. 

To create a new branch and switch to it immediately, use the `switch` command:
```bash
git switch -c my-new-feature
```

### Step 2: Make Your Changes & Add to the Staging Area
Once you've made your changes, you need to prepare them to be saved. This is called **Staging**. 
The staging area is like a shipping box. It allows you to review what you are about to save before you actually tape the box shut. You are telling Git, *"These are the specific files I want in my next snapshot."*

```bash
# To add all changed files at once
git add .
```

### Step 3: Commit Your Changes
Now that your files are in the staging area, it’s time to take the snapshot. Remember, this generates that unique hash! Because the hash is just a number, we add a text message.
```bash
git commit -m "Add new login function"
```

### Step 4: Pull Before You Push! (The Golden Rule)
Before you send your code to the remote server, it is a golden rule to **pull** any new updates that your teammates might have added while you were working. This prevents conflicts!
```bash
git pull origin main
```

### Step 5: Push to Remote
Your changes currently only exist on your computer. To share your progress, you need to **push** your new branch up to the remote repository.
```bash
git push origin my-new-feature
```

> **⚠️ Common First-Time Error!**
> If this is the very first time you are pushing a newly created branch, you might see this error:
> `fatal: The current branch my-new-feature has no upstream branch.`
> 
> Don't panic! This just happens because your new branch exists locally, but doesn't exist on the remote cloud yet. Git is telling you to link them. Simply copy/paste the command Git suggests:
> ```bash
> git push --set-upstream origin my-new-feature
> ```


---
**Navigation:**
🏠 [Home](index.md) | 
📖[1. What is Git?](1-what-is-git.md) | 
🚀 [2. Getting Started](2-getting-started.md) | 
🔄 [3. Daily Workflow](3-daily-workflow.md) | 
🤝[4. Pull Requests](4-pull-requests.md) | 
📋 [5. Issues & Projects](5-issues-and-projects.md)
---
