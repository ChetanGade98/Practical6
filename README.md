# Practical6

Batch 1
________________________________________
Set 1:
1. Jira Setup:
Your team is starting a new project and needs a Jira Cloud instance to track progress. How would you set up a Jira Cloud instance and navigate to the project board?
Answer:
To set up a Jira Cloud instance and view your project board:
Steps:
1.	Go to https://www.atlassian.com/software/jira.
2.	Sign in or create an Atlassian account.
3.	Select Jira Software and choose a Scrum or Kanban template.
4.	Enter a project name and key.
5.	Click Create project.
6.	Once the project is created, go to the sidebar and click Board to view it.
________________________________________
2. Basic Git Operations:
You’ve updated a project file locally and need to push the changes to GitHub. What Git commands would you use to stage, commit, and push the changes?
Answer:
Use these Git commands on Ubuntu:
Steps:
1.	Open terminal in the project folder.
2.	Stage changes:
git add .
3.	Commit changes with a message:
git commit -m "Updated project file"
4.	Push to GitHub:
git push origin main
________________________________________
3. JQL Search:
Your manager asks you to find all Jira issues assigned to you with the status "In Progress." What JQL query would you use to find this information?
Answer:
JQL Query:
assignee = currentUser() AND status = "In Progress"
________________________________________
Set 2:
1. GitHub Repository:
You’re collaborating with a colleague on a new project. How would you create a GitHub repository and share it with your teammate?
Answer:
You can create and share a repository as follows:
Steps:
1.	Go to https://github.com and log in.
2.	Click New Repository.
3.	Add a name, description, and select visibility.
4.	Click Create repository.
5.	After creation, click Settings > Collaborators.
6.	Add your teammate's GitHub username and click Add.
________________________________________
2. Jira Scrum Project:
Your team is following the Scrum methodology. How would you create and configure a new Scrum project in Jira?
Answer:
To create a Scrum project:
Steps:
1.	Log in to Jira Cloud.
2.	Click Projects > Create Project.
3.	Select the Scrum template.
4.	Enter project details and click Create.
5.	Configure boards and sprints from the project’s sidebar.
________________________________________
3. Git Branching:
You want to create a new feature without affecting the main code. How would you create a new branch, switch to it, and merge it back once the feature is complete?
Answer:
Use Git branching as follows:
Steps:
1.	Create new branch:
git branch feature-branch
2.	Switch to it:
git checkout feature-branch
3.	After coding, switch back to main:
git checkout main
4.	Merge the branch:
git merge feature-branch
________________________________________
Set 3:
1. Git Installation:
You’ve set up a new laptop and need to configure Git with your GitHub account. What steps would you take to install Git and link it with your GitHub username and email?
Answer:
Use Ubuntu terminal:
Steps:
1.	Install Git:
sudo apt update && sudo apt install git -y
2.	Set username:
git config --global user.name "Your Name"
3.	Set email:
git config --global user.email "you@example.com"
________________________________________
2. Jira Issue Creation:
You’ve identified a bug in the project. How would you create an issue in Jira, classify it under the appropriate epic, and assign it to a developer?
Answer:
Create and assign an issue in Jira:
Steps:
1.	Go to the project board.
2.	Click Create in the top menu.
3.	Fill in the summary, issue type as Bug, and link it to the relevant epic.
4.	Set the priority and assign the developer.
5.	Click Create.
________________________________________
3. Jira Filter Creation:
You want to track only high-priority issues in your project. How would you create a JQL filter and save it for future use?
Answer:
Use JQL filter like this:
Steps:
1.	Go to Filters > Advanced Issue Search.
2.	Enter query:
priority = High
3.	Click Save As, give it a name, and save the filter.
________________________________________
I'll continue with Set 4 to Set 8 next. Shall I go on?
4o
You said:
yes
ChatGPT said:
Continuing with the remaining sets from Batch 1, here are the answers for:
________________________________________
Set 4:
1. Local Git Initialization:
You’ve just created a new project folder on your local machine. How would you initialize a Git repository and link it to your GitHub repository?
Answer:
Steps:
1.	Open terminal and navigate to the project folder:
cd your-project-folder
2.	Initialize Git locally:
git init
3.	Add files:
git add .
4.	Commit:
git commit -m "Initial commit"
5.	Add remote GitHub repo:
git remote add origin https://github.com/yourusername/your-repo.git
6.	Push to GitHub:
git push -u origin main
________________________________________
2. Git Push and Pull:
How would you pull updates into your local repository without losing your work?
Answer:
Steps:
1.	Save any current changes using:
git add . && git commit -m "Saving local changes"
2.	Pull updates from GitHub:
git pull origin main
3.	If conflicts occur, resolve them manually and re-commit:
git commit -m "Resolved merge conflicts"
________________________________________
3. Jira Dashboard:
You need to create a dashboard in Jira showing open issues, active sprints, and completed tasks.
Answer:
Steps:
1.	Go to Jira and click Dashboards > Create dashboard.
2.	Name the dashboard and set visibility.
3.	Add gadgets:
o	Filter Results for open issues.
o	Sprint Burndown for active sprint.
o	Two Dimensional Filter Statistics for completed tasks.
4.	Save and arrange widgets as needed.
Set 5:
1. Jira Navigation:
How would you find the sprint backlog and the active sprint board?
Answer:
Steps:
1.	Open the Jira project.
2.	In the sidebar, click on Backlog to view sprint backlog.
3.	Click Active sprints to see the current sprint board.
________________________________________
2. Git Commit:
What Git commands would you use to add the file and commit the changes with a descriptive message?
Answer:
Steps:
1.	Add the modified file:
git add filename.ext
2.	Commit with a message:
git commit -m "Updated XYZ functionality"
________________________________________
3. Git Merge:
What steps would you follow to merge a feature branch into the main branch smoothly?
Answer:
Steps:
1.	Switch to main branch:
git checkout main
2.	Pull latest changes:
git pull origin main
3.	Merge feature branch:
git merge feature-branch
4.	Push merged changes:
git push origin main
________________________________________
Set 6:
1. GitHub Setup:
How would you create a GitHub repository with a README.md and .gitignore for .java files?
Answer:
Steps:
1.	Go to GitHub and click New repository.
2.	Enter repo name and description.
3.	Check the boxes for:
o	Add README.md
o	.gitignore > Java
4.	Click Create repository.
________________________________________
2. Jira Epic Creation:
How would you create an epic in Jira and link relevant stories to it?
Answer:
Steps:
1.	Click Create > Select Epic as issue type.
2.	Enter details and click Create.
3.	To link stories:
o	Open story issue
o	In the Epic Link field, choose the created epic.
________________________________________
3. JQL Search:
What JQL query would you use to find all issues in the current sprint that are still open?
Answer:
JQL Query:
sprint in openSprints() AND resolution = Unresolved
________________________________________
Set 7:
1. Git Commit:
How would you add a file and commit the changes with a message?
Answer:
Steps:
1.	Stage the file:
git add filename.ext
2.	Commit it:
git commit -m "Added new changes to XYZ"
________________________________________
2. Git Pull:
How would you pull changes from main without conflicts?
Answer:
Steps:
1.	Make sure your branch is clean:
git status
2.	Pull changes:
git pull origin main
3.	If conflicts appear, resolve and commit again.
________________________________________
3. Jira Board Configuration:
How would you configure a Kanban board in Jira and customize its columns?
Answer:
Steps:
1.	Go to Project settings > Boards > Create Board.
2.	Choose Kanban template.
3.	Name the board and select a project.
4.	Click Board settings > Columns to add or rename columns.
________________________________________
Set 8:
1. JQL Search:
Find all Jira issues assigned to you with the status "In Progress".
Answer:
JQL Query:
assignee = currentUser() AND status = "In Progress"
________________________________________
2. Jira Story Creation:
How would you create a Jira story with appropriate details and assign it to the development team?
Answer:
Steps:
1.	Click Create in Jira.
2.	Choose issue type: Story.
3.	Add title, description, acceptance criteria, priority.
4.	Assign to a developer or team.
5.	Click Create.
3. Git Branching:
How would you create a separate branch for a hotfix and merge it into main without affecting the other feature branch?
Answer:
Steps:
1.	Create hotfix branch:
git checkout -b hotfix-branch
2.	Make changes, then commit:
git add .
git commit -m "Hotfix implemented"
3.	Switch to main and merge:
git checkout main
git merge hotfix-branch
 
________________________________________
Set 9:
1. Jira Cloud Instance:
How would you create user accounts and assign project roles within your Jira Cloud instance?
Answer:
Steps:
1.	Log in to Jira Cloud as an admin.
2.	Go to Settings > User Management.
3.	Click Invite users, enter emails, and select product access.
4.	Open the project, go to Project Settings > People.
5.	Add users and assign roles like Developer, Admin, etc.
________________________________________
2. Git Commit and Push:
How would you stage all the changes, commit them with a message, and push them to GitHub?
Answer:
Steps:
1.	Open terminal and navigate to your project.
2.	Stage all files:
git add .
3.	Commit with message:
git commit -m "Updated project files"
4.	Push to GitHub:
git push origin main
________________________________________
3. JQL Search:
Find issues with the label “Bug” created in the last 7 days.
Answer:
JQL Query:
labels = Bug AND created >= -7d
________________________________________
Set 10:
1. GitHub Repository Setup:
How would you create a repository, add a license file, and enable branch protection rules?
Answer:
Steps:
1.	Go to https://github.com > New Repository.
2.	Fill repo details, check Add a license.
3.	After creation, go to Settings > Branches.
4.	Under Branch protection rules, click Add rule.
5.	Add rule for main and enable “Require pull request reviews”.
________________________________________
2. Jira Sprint Creation:
How would you create a sprint and move backlog items into it?
Answer:
Steps:
1.	Go to the Jira project’s Backlog view.
2.	Click Create Sprint at the top.
3.	Drag backlog issues into the sprint area.
4.	Click Start Sprint, set start and end dates.
________________________________________
3. Git Branch Creation:
How would you create a new branch, switch to it, and push it to GitHub?
Answer:
Steps:
1.	Create branch:
git checkout -b feature-branch
2.	Push to GitHub:
git push -u origin feature-branch
________________________________________
Set 11:
1. Git Installation and Configuration:
How would you install Git and configure it with your GitHub credentials?
Answer:
Steps:
1.	Install Git:
sudo apt update && sudo apt install git -y
2.	Set username:
git config --global user.name "Your Name"
3.	Set email:
git config --global user.email "you@example.com"
________________________________________
2. Jira Issue Creation:
How would you create a Jira issue, set the priority to "High," and assign it to a developer?
Answer:
Steps:
1.	Click Create in Jira.
2.	Select project and issue type (e.g., Bug or Task).
3.	Enter summary and description.
4.	Set priority to High.
5.	Assign to a developer.
6.	Click Create.
________________________________________
3. Jira Dashboard Setup:
How would you create and configure a dashboard showing sprint progress and issue breakdown?
Answer:
Steps:
1.	Go to Dashboards > Create Dashboard.
2.	Name it, set permissions, and click Create.
3.	Click Add Gadget.
4.	Add:
o	Sprint Health
o	Issue Statistics
o	Two Dimensional Filter Stats
5.	Configure each gadget using saved filters.
________________________________________
Set 12:
1. Local Git Initialization:
How would you initialize it as a Git repository and link it to GitHub?
Answer:
Steps:
1.	Navigate to folder:
cd project-folder
2.	Initialize Git:
git init
3.	Add files:
git add .
4.	Commit:
git commit -m "Initial commit"
5.	Add remote:
git remote add origin https://github.com/your/repo.git
6.	Push:
git push -u origin main
________________________________________
2. Git Pull and Merge:
How would you pull changes and handle merge conflicts?
Answer:
Steps:
1.	Pull changes:
git pull origin main
2.	If merge conflicts occur, open files and resolve them.
3.	After resolving, stage files:
git add conflicted-file
4.	Commit:
git commit -m "Resolved merge conflicts"
________________________________________
3. Jira Filter Creation:
How would you create a JQL filter and share it with the team?
Answer:
Steps:
1.	Go to Filters > Advanced Issue Search.
2.	Write query:
assignee in (membersOf("team-name")) AND resolution = Unresolved
3.	Click Save As, name the filter.
4.	Go to Manage filters > Share to share with team.
________________________________________
Set 13:
1. Jira Project Setup:
How would you set up a new Scrum project in Jira and configure permissions?
Answer:
Steps:
1.	Go to Projects > Create Project.
2.	Select Scrum and click Use template.
3.	Fill in project name and click Create.
4.	Go to Project settings > People, add client emails and assign roles.
________________________________________
2. Git Add and Commit:
How would you stage only specific files and commit?
Answer:
Steps:
1.	Stage selected files:
git add file1.js file2.css
2.	Commit:
git commit -m "Updated styles and scripts"
3.	Push:
git push origin main
________________________________________
3. Git Merge:
How to merge a branch into main without fast-forwarding?
Answer:
Steps:
1.	Switch to main:
git checkout main
2.	Pull latest:
git pull origin main
3.	Merge with no fast-forward:
git merge --no-ff feature-branch
4.	Push changes:
git push origin main
________________________________________
Set 14:
1. GitHub Repository Collaboration:
How would you invite an external developer and set access?
Answer:
Steps:
1.	Go to repo > Settings > Collaborators.
2.	Click Invite a collaborator.
3.	Enter GitHub username and click Add.
4.	Set access to Read, Write, or Admin as needed.
________________________________________
2. Jira Epic and Story Linking:
How would you create an epic and link stories to it?
Answer:
Steps:
1.	Create an Epic via Create > Issue Type > Epic.
2.	Add title and description, then click Create.
3.	Open a story issue.
4.	In Epic Link, select your epic.
________________________________________








