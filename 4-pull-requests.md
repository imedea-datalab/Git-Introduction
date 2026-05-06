## 4. Pull Requests (PRs) & Linking Issues

Now that your branch is pushed to the remote repository, it's time to integrate your work into the final code by opening a **Pull Request (PR)**.

A Pull Request says to the team:
1. **"I have made these changes."**
2. **"Can you please check the changes?"**
3. **"If they are correct, please merge the changes from my branch into the `main` branch."**

### But First — What Does "Pulling" Mean?

Remember from [1. What is Git?](1-what-is-git.md) how you and Rosa were working on separate branches? Let's look at the picture again:

![Git Branching — showing the pull step where Rosa gets the latest salinity code from main into her branch](images/git-2.png)

Look at step 3 in the picture: **"Pull new salinity code from main."** What's happening there?

After you finished your new salinity code and merged it into the main branch, the main road now has your updated code. But Rosa is still on her own branch — her branch still has the old salinity code because she branched off before you finished yours.

So Rosa needs to grab the latest changes from the main branch and bring them into her branch. This is called **pulling**. It's like Rosa saying, *"Hey Git, the main road has been updated since I started my branch. Can you bring those updates into my branch so I have the latest code to work with?"*

This is super important because Rosa needs the new salinity code to properly test her temperature plots. After pulling, her branch now has both her temperature work AND your new salinity code. She can test everything together, make sure it all works, and only then open a PR to merge her branch into main.

In short: **pulling = grabbing the latest changes from another branch (usually main) into your own branch** so you stay up to date.

### How to Link and Close Issues from a PR

#### Why Do Issues Matter?

Before we talk about linking, let's talk about **why issues exist in the first place**.

Imagine your team is working on the ocean analysis project and there are many things to do — fix a bug in the salinity formula, add a new temperature map, update the data source, clean up old code. If all of this just lives in people's heads or in random messages, things get lost fast. Who is working on what? What still needs to be done? Did anyone fix that bug Rosa found last week?

**Issues** are like a shared to-do list for your project. Issues belong to a Repository ( Repository is a collection of files and folders that are tracked by Git, it is basically a technical word for - "A PROJECT" ). Each issue is a clear task or problem — for example, *"Issue #12: Fix the salinity formula to handle negative values"* or *"Issue #45: Add a global temperature heatmap."* They give the team a single place to:

- **Keep track of all the work** that needs to be done
- **Assign tasks** — so everyone knows who is responsible for what
- **Discuss the details** — team members can leave comments, ask questions, and share ideas right on the issue before anyone starts coding
- **See the history** — months later, you can look back and understand why a certain change was made

#### Why Link Issues to a PR?

When you open a PR, it's usually because you are solving one of these issues. By linking your PR to the issue, you create a clear connection: *"This code change is the solution to that problem."* 

This is important because:
- **Everyone can trace the work**: Your team can look at Issue #12 and immediately see the PR that fixed it — and click through to see exactly what code was changed.
- **It closes automatically**: When your PR gets merged, the linked issue closes by itself. No need to go back and manually mark it as done.
- **It keeps things organized**: Instead of a pile of random code changes, every change has a reason (the issue) attached to it. This is especially helpful when your project grows and you have dozens of branches and changes flying around.

#### How to Actually Link Them

**Method 1: The Keyword Magic (Automatic)**
In the description of your Pull Request, simply type a closing keyword followed by the issue number. For example, if you are working on Issue #123, you can type:
* `Fixes #123`
* `Closes #123`
* `Resolves #123`
*(When the PR is approved and merged, GitHub will automatically close Issue #123 for you!)*

**Method 2: The Sidebar Method (Manual)**
If you forget to type the keyword, you can link it manually:
1. On the right side of your PR page, look for the **Development** section in the sidebar.
2. Click the **gear icon** (or the **+** button).
3. Search for and select the Issue you want to link.

---
**Navigation:**
🏠 [Home](index.md) | 
📖[1. What is Git?](1-what-is-git.md) | 
🚀 [2. Getting Started](2-getting-started.md) | 
🔄 [3. Daily Workflow](3-daily-workflow.md) | 
🤝[4. Pull Requests](4-pull-requests.md) | 
📋 [5. Issues & Projects](5-issues-and-projects.md)
---
