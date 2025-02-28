# Practical6
Here are the answers to your 
.



3. .



222211111
q
q
q
q
qqq


Jira Setup & Navigation

1. Set up a Jira Cloud instance and navigate to the project board:

Set up Jira Cloud:

Sign up for a Jira Cloud account by visiting Atlassian's website.

Once signed in, you can create a new Jira Cloud instance by clicking on "Create new site" and following the prompts.


Navigate to the project board:

After logging in, go to the "Projects" menu in the top navigation bar and select "Create project."

Choose the project type (e.g., Scrum, Kanban, or another template) and fill in the project details.

Once the project is created, you’ll be taken to the project board. If not, select the project from the "Projects" dropdown.




2. Navigate to the sprint backlog and active sprint board:

From your project board, click on Backlog in the left-hand sidebar. This shows the Sprint Backlog.

To view the active sprint board, click on Active Sprint in the left-hand sidebar, where you'll see the tasks currently in progress for the sprint.



3. Configure a Kanban board and customize columns:

Go to your Jira project.

Click on Board settings (in the top-right corner).

Under Columns, you can customize the board by adding or removing columns, as well as mapping statuses to each column (e.g., To Do, In Progress, Done).

Drag statuses into the respective columns as required, or click on Add column to create new ones.



4. Create and configure a new Scrum project in Jira:

From the Projects dropdown, select Create project.

Choose Scrum as the project template.

Enter the project name, key, and any other required details.

Click Create to generate the Scrum project.

After the project is created, you can configure the boards, sprints, and backlog under the project settings.



5. Create a dashboard to show open issues, active sprints, and completed tasks:

Navigate to Dashboards in the top navigation bar and select Create dashboard.

Choose a layout, and give the dashboard a name.

Add gadgets like:

Filter Results (for open issues).

Sprint Health (to display the current sprint).

Pie Chart or Created vs. Resolved Chart (to display completed tasks).


Configure the gadgets to show data based on your project and desired filters.



6. Create a dashboard for sprint progress and issue breakdown by status:

Follow the same steps as above to create a new dashboard.

Add the following gadgets:

Sprint Health or Burndown Chart (to track sprint progress).

Issue Statistics (to show issues broken down by status like "To Do," "In Progress," "Done").

Customize filters for your specific project or sprint as needed.






---

Jira Issue Management & Filters

7. Create an issue, classify it under an epic, and assign it to a developer:

Go to your Project and click Create in the top menu.

In the Issue Type field, select the appropriate issue type (e.g., Bug).

Under the Epic Link field, select the appropriate Epic.

Assign the issue to a developer in the Assignee field.

Fill in other details (priority, description, etc.) and click Create.



8. Create a critical issue, set priority to "High," and assign it to a developer:

Click Create in the top menu.

In the Priority field, select "High."

Assign it to the developer using the Assignee field.

Provide other relevant details, such as description, and click Create.



9. Create a JQL filter to track high-priority issues:

Go to Issues in the top menu and click on Search for issues.

In the search bar, use the following JQL query:

priority = High AND project = "Your Project Name" AND status != Done

Save the filter by clicking on Save as and give it a name (e.g., "High Priority Issues").



10. Create a JQL filter and share it with the team:

Follow the same steps as above to create a filter.

After saving the filter, click Details and then Share.

You can share the filter with a specific group or project team by choosing the appropriate permissions.



11. Create an epic and link relevant stories to it:

Go to the Backlog of your project.

On the left-hand side, click Create Epic and provide details like name and description.

To link stories, edit the story and set the Epic Link field to the created Epic.



12. Create a Jira story and assign it to the development team:

Click Create from the top menu.

In the Issue Type field, select Story.

Provide relevant details such as the story description.

Assign it to the development team or a specific developer in the Assignee field.

Click Create.





---

Jira Sprint & Epic Management

13. Create a sprint and move backlog items into it:

Go to the Backlog of your project.

Click Create Sprint in the backlog section.

Drag and drop items (user stories, tasks) into the sprint.

When ready, click Start Sprint to begin the sprint.



14. Close the sprint and move incomplete tasks to the next sprint:

Go to Active Sprint and click on Complete Sprint.

Jira will ask if you want to move incomplete issues to the next sprint. Confirm this option, and any remaining issues will be carried over.



15. Onboard new members and assign project roles:

Go to Jira settings > User Management > Invite users.

Enter their email addresses and assign them appropriate roles (e.g., Developer, Scrum Master).

Make sure to provide them with access to the correct projects and boards.



16. Set up a new Scrum project for a client and configure permissions:

Create a new Scrum project as described above.

After creating the project, go to Project settings > Permissions.

Assign the appropriate roles (e.g., Project Lead, Developer) to the client's team members and set up permissions to restrict or allow access as necessary.


444445555.....

JQL Search Queries

17. Find all Jira issues assigned to you with the status "In Progress":



assignee = currentUser() AND status = "In Progress"

18. Find all issues in the current sprint that are still open:



sprint in openSprints() AND status != "Done"

19. Find all issues with the label "Bug" that were created in the last 7 days:



labels = "Bug" AND created >= -7d

20. Find all issues assigned to you, excluding those with the status "Done":



assignee = currentUser() AND status != "Done"

Git & GitHub Basics

21. Set up Git and link it with your GitHub username and email:



Install Git:

On macOS, use: brew install git

On Linux, use: sudo apt-get install git

On Windows, download from the Git website and install.


Configure Git with your username and email:

git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"


22. Update your Git configuration with a new email address:



git config --global user.email "newemail@example.com"

23. Initialize a Git repository and link it to your GitHub repository:



git init
git remote add origin https://github.com/username/repository.git

24. Create a new branch, switch to it, and push it to GitHub:



git checkout -b new-feature-branch
git push -u origin new-feature-branch

25. Create a new branch, switch to it, and merge it back once the feature is complete:



Create and switch to the branch:

git checkout -b new-feature

Work on the feature and commit changes.

Switch to the main branch and merge:

git checkout main
git merge new-feature


26. Create a separate branch for the hotfix and merge it into main:



Create a hotfix branch:

git checkout -b hotfix-branch

Apply the hotfix and commit.

Switch to the main branch and merge:

git checkout main
git merge hotfix-branch

Push the changes:

git push origin main


Git Commit, Merge & Push Operations

27. Stage all changes, commit them with a message, and push to GitHub:



git add .
git commit -m "Your commit message"
git push origin main

28. Stage specific files, commit them with a message, and push to GitHub:



git add path/to/file1 path/to/file2
git commit -m "Your commit message"
git push origin main

29. Add a file and commit the changes with a descriptive message:



git add path/to/file
git commit -m "Descriptive message about the changes"

30. Merge a feature branch into the main branch:



Switch to the main branch:

git checkout main

Merge the feature branch:

git merge feature-branch

Push the changes:

git push origin main


31. Merge a feature branch into main without fast-forwarding:



git checkout main
git merge --no-ff feature-branch
git push origin main

32. Delete the feature branch both locally and on GitHub:



Delete the branch locally:

git branch -d feature-branch

Delete the branch on GitHub:

git push origin --delete feature-branch

555555555777777

GitHub Repository Management

33. Create a GitHub repository and share it with your teammate:


34. Go to GitHub and click on the New button to create a new repository.


35. Enter a name, description, and set the repository to public or private.


36. After creating the repository, click on the Settings tab, then Collaborators.


37. Type your teammate's GitHub username and invite them to the repository by clicking Add collaborator.


38. Your teammate will receive an invitation to join the repository, which they can accept.


39. Create a GitHub repository with a README.md and a .gitignore for Java:


40. Go to GitHub and create a new repository.


41. During the creation process, check the box to Initialize this repository with a README.


42. Choose Add .gitignore and select Java from the template dropdown.


43. After the repository is created, clone it to your local machine:

git clone https://github.com/username/repository.git


44. Create a GitHub repository, add a license file, and enable branch protection rules:


45. Create the repository on GitHub.


46. After the repository is created, go to the Settings tab.


47. Under the Code and automation section, select Licenses and choose a license (e.g., MIT, GPL, etc.).


48. To enable branch protection rules, go to Branches, select Add Rule, and specify the rules you want (e.g., require pull request reviews before merging).


49. Invite an external developer to a GitHub repository and set the access level:


50. Go to the Settings tab of the repository.


51. In the Collaborators & Teams section, click on Manage Access.


52. Click Invite a collaborator, enter their GitHub username, and choose the appropriate access level (e.g., Read, Write, or Admin).


53. The external developer will receive an invitation to join the repository, which they can accept.




---

Git Pull, Merge & Conflict Resolution

37. Pull updates from GitHub into your local repository without losing your work:


38. First, commit any local changes you have:

git add .
git commit -m "Your message"


39. Pull the latest changes from the remote repository:

git pull origin main


40. If there are conflicts, Git will notify you. Resolve the conflicts, stage the changes, and commit the merge:

git add conflicted-file
git commit -m "Resolved conflicts"


41. Pull changes from your teammate’s branch and handle merge conflicts:


42. First, commit your local changes if you haven’t already:

git add .
git commit -m "Your message"


43. Pull the changes from the remote branch:

git pull origin teammate-branch


44. If there are conflicts, Git will mark the conflicted files. Open the conflicted files and resolve the conflicts.


45. Stage the resolved files and commit the merge:

git add conflicted-file
git commit -m "Resolved merge conflicts"


46. Pull updates from the main branch into your feature branch without conflicts:


47. First, make sure you have committed your local changes:

git add .
git commit -m "Your message"


48. Fetch the latest changes from the main branch:

git fetch origin


49. Merge the changes into your feature branch:

git merge origin/main


50. If there are no conflicts, the merge will complete automatically. If there are conflicts, resolve them and commit the changes as described in step 38.












