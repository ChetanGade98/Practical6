# Practical6
Here are the answers to your questions:


---

1. Jira Setup:

To set up a Jira Cloud instance and navigate to the project board, follow these steps:

1. Create a Jira Cloud Account:

Go to Jira Cloud and sign up or log in with your existing Atlassian account.



2. Create a New Jira Cloud Instance:

Once logged in, you'll be directed to your Jira dashboard. If you don’t have a Jira instance, you can create a new one by selecting "Create Project" from the dashboard or choosing the "Get Started" button.



3. Choose a Project Template:

Jira offers various project templates (Scrum, Kanban, etc.). Choose the one that suits your project. For example, if you're using an Agile method, select the Scrum or Kanban template.



4. Set Up Your Project:

Enter the project name, key (for short reference), and configure other settings like the project lead and permissions.



5. Navigate to the Project Board:

Once the project is created, go to the sidebar on the left, and under "Projects," select the project you just created. This will open the project board where you can manage your tasks and view various project activities.





---

2. Basic Git Operations:

To push the updated project file to GitHub, follow these Git commands:

1. Stage Changes:

git add <file-name>  # Stages the updated file for commit

Or to stage all modified files:

git add .


2. Commit Changes:

git commit -m "Your commit message describing the changes"


3. Push Changes to GitHub:

git push origin <branch-name>  # Pushes changes to the specified branch on GitHub



For example, if you're working on the main branch:

git push origin main


---

3. JQL Search:

To find all Jira issues assigned to you with the status "In Progress," use the following JQL (Jira Query Language) query:

assignee = currentUser() AND status = "In Progress"

This will return all issues where the assignee is the current logged-in user and the status is "In Progress."


---

Let me know if you need further clarification on any of the topics!

222.2.2.222222222.2.2.2.2.22

1. GitHub Repository:



To create a GitHub repository and share it with your teammate:

1. Create the repository:

Go to GitHub and log in.

Click on the + icon in the top right corner and select New repository.

Name your repository, add a description, and choose whether it’s public or private.

Optionally, initialize the repository with a README.md and a .gitignore file.

Click Create repository.



2. Clone the repository to your local machine:

After creating the repository, you'll be directed to the repository page.

Copy the repository URL (HTTPS or SSH).

Clone the repository to your local machine:

git clone https://github.com/your-username/your-repository-name.git



3. Share the repository with your teammate:

Go to the Settings tab of the repository on GitHub.

Under Collaborators & teams, add your teammate's GitHub username or email address to invite them as a collaborator.

Your teammate will receive an invitation to access the repository.



4. Your teammate can now clone the repository:

git clone https://github.com/your-username/your-repository-name.git


5. Jira Scrum Project:



To create and configure a new Scrum project in Jira:

1. Create a new Scrum project:

In Jira, go to the main dashboard.

Click on the Create project button.

Choose Scrum Software Development under Project templates.

Enter the project name, key, and select a project lead.

Click Create to generate the project.



2. Configure the Scrum board:

After creating the project, go to the Board (or Active Sprint) view.

Set up your board settings by going to Board settings under the three-dot menu on the top right.

Configure columns, filters, and issue types according to your team’s needs.



3. Add and manage sprints:

In the backlog view, create sprints by clicking the Create Sprint button.

Add stories and tasks to each sprint by dragging them into the sprint.

Once your team is ready, start the sprint by selecting Start Sprint and setting the duration and dates.



4. Git Branching:



To create a new branch, switch to it, and merge it back once the feature is complete:

1. Create a new branch:

First, make sure you are on the main branch (or the default branch):

git checkout main

Create a new branch for the feature:

git checkout -b feature-branch-name



2. Work on the feature and commit your changes:

Make changes to your code, and when you're ready to commit, add and commit them:

git add .
git commit -m "Add feature X"



3. Push the branch to the remote repository:

Once you're done with the feature locally, push the branch to the GitHub repository:

git push origin feature-branch-name



4. Create a pull request (PR):

Go to GitHub, navigate to the repository, and you'll see an option to Compare & pull request for the feature branch.

Open a pull request to merge your feature branch into the main branch.



5. Merge the pull request:

Once the pull request is reviewed and approved, merge it into the main branch.

After merging, delete the feature branch (optional):

git branch -d feature-branch-name  # Delete locally
git push origin --delete feature-branch-name  # Delete remotely



6. Update your local main branch:

After merging the feature branch, make sure your local main branch is up to date:

git checkout main
git pull origin main




This process ensures you work on isolated features without affecting the main codebase until everything is ready for integration.


