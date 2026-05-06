# What is Git? And how it works
At its core, **Git is a Version Control System (VCS)** ( Explained below, what this technical term means ).
Imagine you have a piece of code—perhaps a script for analyzing ocean temperature data. On day one, the code looks very different than what it looks like after you have worked on it for a few days. 

Because your code naturally evolves, at each step it would be nice to have a place where you can see snapshots or a timeline record of how the code changed each day (like day 1, day 2, etc.). With Git, you have exactly that! Whenever you want—whether that's every day, every hour, or every few minutes—you can tell Git, *"Hey, record what my code looks like right now."* 
This is called **Version control**, each snapshot, or change in your code is kind of a new version of your code. And you are keeping a record of it or controling ( in git if you seee any mistake with one snapshot or version you can go back to any previous snapshot or version and fix it. This is the best part of version control! ) it. 

This instruction - *"Hey, record what my code looks like right now."* - to save a record is called a **commit**. 

When you commit:
1. Git takes your whole code and all the files, and passes them through an algorithm.
2. This algorithm outputs or generates a **unique ID** (a long string of numbers and letters called a *hash*).
3. If you change even a single letter in your code—like updating a salinity threshold—and tell Git to commit again, the algorithm generates a brand new unique ID. 

This means Git always knows exactly what snapshot of your code you are looking at.

Here is a picture to help you visualize how this works:

![Git Version Control Timeline — each circle represents a full snapshot of your entire project at that point in time](images/git-1.png)

One important thing to understand from this picture: each circle (Version 1, Version 2, Version 3) is **not** just the specific lines you changed in your code. Each version is actually a snapshot of your **entire set of files** in your project — all the scripts, data files, everything. So when Git saves a version, it saves the whole picture of your project at that moment. 

Then, when you want to see what actually changed between, say, Version 1 and Version 2, Git compares the two full snapshots and shows you just the differences — the exact lines that were added, removed, or modified. That's how you can always tell exactly what changed and when.

## Why is this helpful?

#### 1. Going Back in Time to Fix Mistakes

Let's say you and Rosa are working on the same project but different parts of it. You work on the salinity part and Rosa on the temperature part. Rosa updated the algorithm for the temperature part, and you updated the algorithm for the salinity part. But later you realised that you made a mistake in your salinity update. The solution sounds simple — just go back and fix it. But do you remember exactly which lines and variables you changed the last time you worked on your 500 lines of code? And do you remember exactly what lines Rosa added to the script? Because you want to correct your mistakes, but you don't want to accidentally delete anything Rosa added.

If you use Git to track your code changes, versions, and snapshots, you can easily fix your mistakes. You can go back to the exact previous version of your code, see exactly what you changed, and fix only the parts that need fixing. And then you can apply Rosa's part to your code too — because Rosa was also using Git, her part is saved as a separate version.

#### 2. Everyone Has Their Own Copy (Work Offline!)

Imagine your team is working on a shared analysis script. Rosa is at the lab in Barcelona, and you are out on a research vessel in the middle of the Atlantic — with no internet for the next two weeks. Without Git, you'd be stuck. You can't access the shared project, and any code you write on your laptop is completely disconnected from what the team is doing back on land.

With Git, this isn't a problem at all. When you set up Git on a project, every person on the team gets a **full copy** of the entire project and all of its history on their own computer. So even on that boat with zero Wi-Fi, you can keep writing code, making commits, and tracking your changes — all locally on your laptop. When you're back at port and have internet again, you just sync your changes with the rest of the team. Rosa's work from Barcelona and your work from the Atlantic all come together, with the full history intact.

#### 3. Working on Different Things at the Same Time (Branching)

Now here's where it gets really powerful. Remember how we said Git keeps a timeline of snapshots? Think of that timeline as a straight line — commit after commit, one after the other.

But what if you and Rosa need to work on different things at the same time? You want to change the current salinty code to a new salinty code ( and this will take you a week to finish). And, Rosa wants to completely rewrite the temperature plotting. If you're both making changes on the same timeline, things can get messy fast — your half-finished updated salinty code might break Rosa's temperature plotting code. Because she may need to use the salinty code ( old salinty code or the new salinty code which you will finish this week, yours is not ready yet and is incomplete, so untill you finish your new salinty code, rosa cannot use it to plot the temperature ) to plot the temperature, and vice versa.

This is where **branching** comes in. A branch is basically taking a copy of that timeline and starting your own separate timeline from that point. Think of it like a fork in the road. The main road (called `main`) keeps going straight, and you take a side road to work on your salinity filter. Rosa takes a different side road ( which includes the old salinity code ) to work on her temperature plots. And you take another which includes the old temperature code. You each make commits on your own road without affecting each other — or the main road. Then when you both finish your work you can merge your side roads back into the main road. So now the main road has both of your changes, and nobody's work got broken along the way.

Here is a picture that shows exactly how this works:

![Git Branching — Rosa and you each work on separate branches, then merge back into the main road](images/git-2.png)

In this picture you can see that you (Me) created a branch to work on the new salinity code, and Rosa created a branch to rewrite the temperature plots. You both started from the same shared code (the starting point). You each made your commits independently — without breaking each other's work. When you finished your salinity code, you merged it back into the main road. Rosa then **pulled** the updated main code (which now has your new salinity code) into her branch so she could test her temperature plots with it. Once she was satisfied, she opened a PR and merged her branch into main too. Now the main road has both new features!

*(Don't worry about what "pulling" means just yet — we'll explain that in detail in [4. Pull Requests](4-pull-requests.md).)*

#### 4. Reviewing Each Other's Work Before It Goes In

Here's the cherry on top. When Rosa finishes her temperature plotting rewrite on her branch and wants to merge it into the main code, she doesn't just dump it in. Instead, she opens something called a **Pull Request (PR)** (we'll cover this in detail here [4. Pull Requests](4-pull-requests.md) ). PR is basically Rosa saying, *"Hey team, I've finished my changes. Can someone take a look before we add this to the main project?"*

The main branch is sacred, it contains the code which is tested and is working fine. So, before merging any branch into the main branch, it should be reviewed by the team members. And the final and the true code lives in the main branch. This ensures the main code is stable and reliable. When you have to make the changes in the main code, you should first create a branch, make the changes in the branch, and then open a PR to merge it into the main branch. That way, the main code remains untouched until the changes are reviewed and approved by the team members.

You (or anyone else on the team), who is reviewing the PR can then look at exactly what Rosa changed — line by line. You can leave comments on her code like *"Hey Rosa, I think this formula should use Celsius, not Fahrenheit."* Only after the team agrees the changes look good do they get merged into the main code. This way, bugs and mistakes get caught early, and everyone stays on the same page.

*(Note: Git will track every file in your project folder, except for the ones you explicitly tell it to ignore using a special file called `.gitignore`. This is where we hide passwords, temporary files, and heavy local installations).*

#### 5. Everything Lives in Two Places: Your Computer and the Cloud

This is something that confuses a lot of beginners, so let's make it crystal clear.

In Git, your project doesn't just live in one place — it lives in **two places at the same time**:

1. **Locally** — on your own computer (your laptop, your workstation, whatever you're coding on).
2. **Remotely** — on a server in the cloud (like GitHub, GitLab, etc.). This is where the whole team can see and access the project.

And here's the key part: **this applies to everything — the main branch, any new branches, all of it.**

The `main` branch? It exists on the remote server (the cloud), **and** it also exists on your local computer as a copy. When Rosa creates a branch called `temperature-plots`? That branch starts on her local computer, **and** she also pushes it up to the remote server so others can see it.

Think of it like this: the remote (cloud) version is the **shared, official copy** that everyone on the team can access. Your local version is your **personal workspace** where you make changes before sharing them.

**So how does your code actually get from your computer to the main project?** It's a multi-step journey. Let's walk through it:

**Step 1: You create a branch on your local computer.**
You say, *"I want to work on the salinity code."* So you create a new branch locally. Right now, this branch only exists on your machine — nobody else can see it yet.

**Step 2: You make changes and commit them locally.**
You write your code, test it, and when you're happy with a chunk of work, you commit it. These commits are saved on your local branch. Still, nobody else can see your work — it's all on your laptop.

**Step 3: You push your local branch to the remote (cloud).**
When you're ready to share your work (or just want a backup in the cloud), you **push** your branch. This uploads your branch and all its commits to the remote server. Now your branch exists in both places — on your computer and on the cloud. Your teammates can now see your branch on GitHub.

**Step 4: You open a Pull Request to merge your remote branch into the remote main branch.**
Here's the thing — even though your branch is now on the remote server, it's still separate from the main branch. Your code is sitting on your branch, not on main. To get it into main, you open a **Pull Request** (PR) on GitHub. This is you saying, *"Hey team, my branch is ready. Please review it and merge it into main."*

**Step 5: After review, your branch gets merged into main on the remote.**
Once the team approves your PR, your changes get merged into the `main` branch — on the remote server. Now the official, shared main branch has your new code!

**Step 6: Everyone pulls the updated main branch to their local computer.**
After the merge, the remote `main` is updated, but everyone's local copy of `main` is still the old version. So each team member (including you!) needs to **pull** the latest version of `main` from the remote to their local computer to stay up to date.

Here's a simple way to remember the whole flow:

> **Local branch → Push to → Remote branch → Pull Request → Remote main → Pull to → Local main**

It's a multi-step process, but each step has a clear purpose: you work locally so you don't break anything for others, you push to the remote so the team can see your work, and you merge through a Pull Request so the code gets reviewed before it goes into the main project.

---
**Navigation:**
🏠 [Home](index.md) | 📖[1. What is Git?](1-what-is-git.md) | 🚀 [2. Getting Started](2-getting-started.md) | 🔄 [3. Daily Workflow](3-daily-workflow.md) | 🤝 [4. Pull Requests](4-pull-requests.md) | 📋[5. Issues & Projects](5-issues-and-projects.md)
---
