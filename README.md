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








