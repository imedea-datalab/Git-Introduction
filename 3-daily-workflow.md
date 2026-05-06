## 3. The Daily Git Workflow

Now that you know what Git is and why it's useful (see [1. What is Git?](1-what-is-git.md)), let's talk about what you actually do every day when working with Git. It's a simple step-by-step process — once you do it a few times, it becomes second nature.

### Step 1: Create a New Branch
Remember how we talked about branching? The main branch has all the final, tested code. You never want to mess with it directly. So the first thing you do is create your own branch — your own side road — to work on.

```bash
git switch -c my-new-feature
```

This creates a new branch called `my-new-feature` and switches you to it right away. From here, all the changes you make only happen on your branch.

### Step 2: Make Your Changes & Stage Them
You've written some code, changed a few files — great! But before you can save a snapshot (a commit), you need to tell Git **which files** you want to include in that snapshot.

This step is called **staging**, and it's like packing a suitcase before a trip. You might have changed 5 files, but maybe only 3 of them are ready to go. Staging lets you pick exactly which ones go into the next commit. The rest stay behind — you can include them in a future commit when they're ready.

To add all your changed files at once (put everything in the suitcase):
```bash
git add .
```

**💡 Tip:** If you staged everything but realize you don't want to include some files, no worries! In VS Code, just open the **Source Control sidebar** (the little branch icon on the left). You'll see all your staged files listed there — simply click the **−** (minus) button next to any file to unstage it. Easy.

**🚫 Files you NEVER want to track:** Some files should never end up in Git at all. For example:
- **Large data files** (like your ocean datasets) — GitHub has a file size limit and isn't designed to store big data files.
- **Secrets and passwords** (like API keys or database credentials) — if your repository is public, anyone on the internet can see them!

For these, you add them to a special file called **`.gitignore`**. Anything listed in `.gitignore` is completely invisible to Git — it won't track them, stage them, or include them in any snapshot. Ever.

### Step 3: Commit Your Changes
Now your files are staged and ready. It's time to take the snapshot — this is the **commit** we talked about in [1. What is Git?](1-what-is-git.md). Remember, Git will generate a unique hash for this snapshot. Since hashes are just long unreadable numbers, we always add a short message describing what we changed:

```bash
git commit -m "Add new login function"
```

### Step 4: Pull Before You Push! (The Golden Rule)
Before you send your code to the remote server, always **pull** first (see [4. Pull Requests](4-pull-requests.md) for a detailed explanation of what pulling means). This grabs any new updates that your teammates might have added while you were working, so your code stays up to date and you avoid conflicts.

```bash
git pull origin main
```

### Step 5: Push to Remote
Right now your changes only exist on your computer. To share your work with the team, you need to **push** your branch up to the remote repository (the shared version that lives online).

```bash
git push origin my-new-feature
```

> **⚠️ Common First-Time Error!**
> If this is the very first time you are pushing a newly created branch, you might see this error:
> `fatal: The current branch my-new-feature has no upstream branch.`
> 
> Don't panic! This just means your new branch exists on your computer, but doesn't exist on the remote server yet. Git is simply asking you to link them. Just copy and paste the command Git suggests:
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
