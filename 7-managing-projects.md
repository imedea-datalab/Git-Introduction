# 7. Mastering Issues & GitHub Projects

While Git tracks your code, **GitHub Projects and Issues track your team's workflow.** 

Our Project Board is the central hub where we plan, discuss, and track everything. It's built around columns that represent the status of a task, typically:
* **Future / Backlog:** Ideas or tasks we want to do, but not right now.
* **To-Do:** Tasks that are ready to be picked up by someone.
* **Ongoing / In Progress:** Tasks someone is actively working on.
* **Done:** Completed and merged tasks.

---

## The 3 Ways to Add Items to a Project Board

When you click to add an item to our Project Board, it's important to understand the three distinct options GitHub gives you:

### 1. Create Issue (Real Issue)
If you use the "Create new issue" option from within a project, GitHub **requires you to select a repository**. An issue *cannot* exist without a home repo!
* **How to identify it:** It will have a green circle icon and a specific issue number (e.g., `#6`) next to the name, and the repository name will be visible above the title.
* **Purpose:** This is an official task ticket ready for work. 

### 2. Create Draft Issue (Virtual Item)
A Draft Issue is a "virtual" item that exists *only* on your project board.
* **How to identify it:** It has no repository, no issue number, and features a distinct "draft" icon next to it.
* **Purpose:** Use this for quick ideas, reminders, or notes that you aren't ready to officially "file" into a repository yet. *(Note: You can easily convert a Draft into a real Issue later!)*

### 3. Add Item from Repository
This option doesn't create anything new. It simply searches for issues that *already exist* in a repository and "links" them to your board so you can track them in your columns.

---

## Anatomy of a Great Issue (Your Workspace)

Once an issue is created, it becomes the **Single Source of Truth** for that specific task. Here is how we use it:

* **Requirements & Deliverables:** The main description of the Issue is where you document exactly what needs to be built. Put your acceptance criteria and requirements here.
* **Notes & Keeping the Conversation Tracked:** As you do your "doings," don't let knowledge get lost in Slack! Write your notes, findings, and comments directly inside the Issue thread. This creates a permanent, searchable history of *why* decisions were made.
* **Assignees:** You can allocate **Assignees** on the right sidebar. Always assign yourself to an issue when you start working on it (move it to "Ongoing") so the team knows who is handling what.
* **Attach PRs and Issues:** As mentioned in previous sections, use the sidebar or type `#` to link Pull Requests to the Issue. 

---

## Filtering and Finding Your Work

Project boards can get crowded. Thankfully, GitHub Projects allows you to filter the board to see only what matters to you!
* Click the "Filter" search bar at the top of the project.
* Type `assignee:@me` to instantly see only the tasks allocated to you.
* You can also filter by `status:To-Do` or search for specific keywords.

---

## 💎 Bonus Pro-Tips for Issues
To make our workflow even better, try using these features:

**1. Markdown Checklists**
If your task has multiple deliverables, you can create interactive checkboxes inside the issue description. Just type `- [ ]` and GitHub turns it into a clickable box!
```markdown
-[x] Create the new database table
- [ ] Write the API endpoint
- [ ] Test the integration
```
*(GitHub will even show a progress bar for these on the project board!)*

**2. Labels**
On the right sidebar of an Issue, you can add color-coded **Labels** (e.g., `bug 🐛`, `enhancement ✨`, `help wanted 🙏`). This makes filtering the board much easier for everyone.

**3. Close with a Comment**
When you finish a task, don't just close it silently. Add a final comment summarizing the fix or linking to the merged PR, then click "Close Issue."

---
**Navigation:**
[8. Permissions](8-permissions.md)
---

