# 1. What is Git?

At its core, **Git is a Version Control System (VCS)**. Its main job is to track the progress and history of your code. 

Think of Git as a camera for your project. As you work, it takes **snapshots** of your code. 

* **The Hash:** Every time Git takes a snapshot, it assigns it a unique identifier called a *hash* (a long string of numbers and letters). 
* **The Sensitivity:** If you change even a single digit or character in your code, the hash completely changes, generating a brand new identifier.
* **The Commit:** Each of these saved snapshots is called a **commit**. Because hashes are just long, unreadable numbers, we attach a human-readable "commit message" to each snapshot so we know exactly what changed.

*(Note: Git will track every file in your project folder, except for the ones you explicitly tell it to ignore using a special file called `.gitignore`. This is where we hide passwords, temporary files, and heavy local installations).*

---
**Navigation:**
🏠 [Home](index.md) | 📖[1. What is Git?](1-what-is-git.md) | 🚀 [2. Getting Started](2-getting-started.md) | 🔄 [3. Daily Workflow](3-daily-workflow.md) | 🤝 [4. Pull Requests](4-pull-requests.md) | 📋[5. Issues & Projects](5-issues-and-projects.md)
---
