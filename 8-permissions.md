# 8. How to Enforce Code Reviews

You can enforce code reviews using **"Branch Protection Rules"** (GitHub) or **"Protected Branches"** (GitLab). These settings also allow you to grant specific people "bypass" privileges, meaning they can push or merge directly to the branch without needing a review.

## Setting this up in GitHub

### 1. Enable Reviews
1. Navigate to your repository **Settings**.
2. In the left sidebar, click on **Branches**, then click **Add rule** (or edit an existing one).
3. Enter `main` (or your default branch) as the **Branch name pattern**.
4. Check the box for **Require a pull request before merging**.
5. Check **Require approvals** and set the number of reviewers you want (usually 1 or 2).

### 2. Add Exceptions (Bypass Privileges)
1. Within that same rule, scroll down and check the box for **Allow specified actors to bypass required pull requests**.
2. Search for and add the specific users or teams who are allowed to merge without a review.

> **📝 Note for Admins:** 
> If you are the repository owner, you can check **Include administrators** to ensure the rules apply to you as well. If you leave it unchecked, you will automatically give yourself a "bypass."

---
**Navigation:**
- [7. Mastering Issues & GitHub Projects](7-managing-projects.md)  
- [8. Permissions](8-permissions.md)
---
