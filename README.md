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








