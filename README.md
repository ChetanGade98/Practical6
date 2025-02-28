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

3333.33333333333333.333333333

1. Git Installation and Configuration:

To install Git and link it with your GitHub account, follow these steps:

a. Install Git:

For Windows:

1. Download the Git installer from the official site: Git for Windows.


2. Run the installer and follow the installation prompts (you can accept the default settings).



For macOS:

1. Open the Terminal and type git --version. If Git is not installed, it will prompt you to install it via Xcode Command Line Tools. Follow the on-screen instructions.



For Linux:

Debian/Ubuntu: Run sudo apt install git.

Fedora: Run sudo dnf install git.

Arch: Run sudo pacman -S git.



b. Configure Git with your GitHub account:

1. Open your terminal/command prompt.


2. Set your username and email address:

git config --global user.name "Your GitHub Username"
git config --global user.email "your-email@example.com"


3. To verify your configurations, run:

git config --global --list



c. Link Git to GitHub (using SSH or HTTPS):

Using HTTPS (simple method):

Clone a repository with:

git clone https://github.com/username/repository.git

GitHub will prompt for your username and password (you may want to use a GitHub token instead of your password).


Using SSH (more secure method):

1. Generate an SSH key:

ssh-keygen -t rsa -b 4096 -C "your-email@example.com"


2. Add the SSH key to the ssh-agent:

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa


3. Add the public key to your GitHub account:

Copy the public key: cat ~/.ssh/id_rsa.pub.

Go to GitHub > Settings > SSH and GPG Keys > New SSH Key.



4. Test the connection:

ssh -T git@github.com




2. Jira Issue Creation:

To create an issue in Jira and classify it under the appropriate epic, follow these steps:

a. Create the Issue:

1. Log in to your Jira account.


2. Click on the "Create" button (usually located in the top navigation bar).


3. Fill out the following fields:

Project: Select the project you're working on.

Issue Type: Choose the issue type, for example, Bug (since it's a bug).

Summary: Provide a brief title for the bug (e.g., "App crashes when clicking the login button").

Description: Give a detailed description of the bug and steps to reproduce it.

Priority: Set the priority (e.g., Critical, Major, Minor).




b. Assign the Issue to a Developer:

1. Under the Assignee field, select the developer responsible for fixing the bug.


2. Alternatively, if you're unsure, you can leave it unassigned or select the default assignee.



c. Classify the Issue under the Appropriate Epic:

1. Look for the Epic Link field (typically in the right panel or within the "More Fields" section).


2. Select the correct Epic from the dropdown list to link the bug to an existing epic.



d. Create the Issue:

1. After filling in all necessary fields, click Create.



3. Jira Filter Creation:

To create a Jira Query Language (JQL) filter for tracking high-priority issues, follow these steps:

a. Navigate to Filters:

1. Go to the Filters tab in Jira (usually at the top).


2. Click on Advanced issue search to open the search screen.



b. Create the JQL Filter:

1. In the JQL search box, enter the following query to track only high-priority issues:

priority in (High, Urgent) AND resolution = Unresolved ORDER BY created DESC

This will filter issues that are either "High" or "Urgent" priority and have not been resolved yet, ordered by the creation date.

You can modify the filter based on the exact priorities or other criteria specific to your project.



c. Save the Filter:

1. After running the search, click on the Save As button.


2. Give your filter a name (e.g., "High-Priority Unresolved Issues").


3. Optionally, add a description for the filter.


4. Click Save.



You can now access this saved filter from the Filters tab in the future and even share it with your team.

4444444..4.4.4.4.44444444

1. Local Git Initialization and Linking to GitHub Repository:

To initialize a Git repository and link it to your GitHub repository, follow these steps:

1. Navigate to your project folder: Open a terminal or command prompt and navigate to your project folder.

cd /path/to/your/project


2. Initialize Git in your project: Initialize an empty Git repository in your project folder.

git init


3. Add remote GitHub repository: Link your local repository to the remote GitHub repository. Replace <repository-url> with your GitHub repository URL.

git remote add origin https://github.com/username/repository-name.git


4. Add files and commit: Add all files to the staging area and commit them.

git add .
git commit -m "Initial commit"


5. Push the changes to GitHub: Push your local commits to the remote GitHub repository.

git push -u origin master  # or main if that's your default branch




---

2. Git Push and Pull:

To pull the updates from GitHub without losing your work, follow these steps:

1. Ensure your local changes are committed: First, commit any local changes you have made.

git add .
git commit -m "Your commit message"


2. Pull the updates from GitHub: Before pulling, it's a good practice to check if your local branch is ahead of the remote branch.

git fetch origin


3. Resolve conflicts (if any): Now, you can pull the changes from GitHub and Git will attempt to merge the changes with your local files.

git pull origin master  # or main if that's your default branch

If there are any merge conflicts, Git will prompt you to resolve them manually. After resolving conflicts:

git add .
git commit -m "Resolved merge conflicts"


4. Push your local changes back to GitHub: Once you've resolved the merge, you can push your local changes back to GitHub.

git push origin master  # or main if that's your default branch




---

3. Creating a Jira Dashboard:

To create a Jira dashboard that shows open issues, active sprints, and completed tasks, follow these steps:

1. Navigate to your Jira Dashboard:

Log in to Jira.

Click on "Dashboards" from the top menu.

Click on "Create New Dashboard."



2. Configure Dashboard Settings:

Provide a name for your dashboard (e.g., "Project Overview").

Set visibility options depending on whether you want the dashboard to be shared with specific users, groups, or remain private.

Click "Create."



3. Add Gadgets to the Dashboard: After creating the dashboard, you can start adding gadgets to display the relevant information.

For Open Issues:

Click "Add Gadget" and search for the "Filter Results" gadget.

Configure the gadget to show open issues by selecting an appropriate filter (e.g., issues with status "Open," "To Do," or similar).


For Active Sprints:

Add a "Sprint Health" or "Agile Sprint" gadget.

Configure it to display the details of the active sprints for your project.


For Completed Tasks:

Add a "Filter Results" gadget again.

Configure it to display completed tasks (e.g., issues with status "Done" or similar).




4. Save and Arrange: After adding these gadgets, you can arrange them on the dashboard by dragging them into the desired positions.


5. Save and Share the Dashboard: Once you are satisfied with the layout, click Save. If you want to share the dashboard with others, ensure you configure the permissions accordingly.



Now, your Jira dashboard will show all open issues, active sprints, and completed tasks, offering a comprehensive view of the project's status.


55555
5
5555555555.5.5.5.5
1. Jira Navigation:

To find the sprint backlog and the active sprint board in Jira:

Sprint Backlog:

1. Go to your Jira dashboard.


2. Click on "Projects" in the navigation bar.


3. Select the project you're working on.


4. Navigate to the "Backlog" section in the sidebar.


5. Here you can see the Sprint Backlog for the current sprint or any upcoming ones.



Active Sprint Board:

1. From your Jira dashboard, go to "Projects".


2. Select the same project.


3. In the sidebar, click on "Active sprints".


4. This will show the active sprint board, where you can track the current sprint's progress and tasks.




2. Git Commit:

If you've made changes to a file but haven't staged or committed them yet, follow these steps:

1. Stage the file(s):

git add <file_name>  # For a specific file
# Or use `git add .` to stage all modified files


2. Commit the changes with a descriptive message:

git commit -m "Descriptive message explaining the changes"



3. Git Merge:

To merge a feature branch into the main branch and ensure a smooth merge, follow these steps:

1. Switch to the main branch (assuming it’s named main):

git checkout main


2. Make sure your main branch is up to date:

git pull origin main


3. Merge the feature branch into the main branch:

git merge <feature-branch-name>


4. Resolve any merge conflicts if they occur. Git will mark conflicted files, and you'll need to edit them manually.


5. Stage and commit the resolved conflicts if there were any:

git add <conflicted-file>
git commit -m "Resolved merge conflict"


6. Push the changes to the remote repository:

git push origin main



This ensures a smooth and conflict-free merge (if no conflicts exist).

666666666..666666666666
1. GitHub Setup (Creating a GitHub Repository with README.md and .gitignore for Java):

To set up a GitHub repository for a Java project with a README.md and .gitignore, follow these steps:

1. Create the Repository:

Go to GitHub and log in.

Click on the "+" button on the top-right corner and select "New repository."

Provide a repository name and description, choose public/private visibility, and check "Initialize this repository with a README."

Click on "Create repository."



2. Add .gitignore for Java:

Once the repository is created, click on the "Add file" button and select "Create new file."

Name the file .gitignore.

Inside the .gitignore file, you can use a predefined Java .gitignore template, which typically looks like:

# Java
*.class
*.log
*.jar
*.war
*.ear
/target/
/bin/
/build/
.classpath
.project
.settings/
.idea/
*.iml

Commit the .gitignore file.



3. Edit the README.md:

You can modify the existing README.md to include a brief description of the project, its purpose, and usage instructions.



4. Push Local Project (Optional):

If you're working with a local project, you can push it to this GitHub repository:

git init
git remote add origin <repository-url>
git add .
git commit -m "Initial commit"
git push -u origin main





---

2. Jira Epic Creation:

To create an Epic in Jira and link relevant stories/tasks to it:

1. Create the Epic:

In Jira, go to the project where you want to create the Epic.

Navigate to the "Backlog" view.

On the left sidebar, you'll see an option for "EPICS." Click on it.

Click the "Create Epic" button or "Create Issue" and select "Epic" as the issue type.

Fill in the Epic details such as Summary (Title), Description, and any other necessary fields.

Click "Create."



2. Link Stories to the Epic:

Once the Epic is created, open the individual stories you want to link to the Epic.

In the issue details, find the "Epic Link" field (typically in the right panel).

Select the relevant Epic from the dropdown list or search for it by name and link it.


Alternatively, you can bulk-edit multiple stories from the backlog and assign them to the Epic at once.




---

3. JQL Search for Open Issues in the Current Sprint:

To find all issues that are still open in the current sprint, you can use the following JQL (Jira Query Language) query:

sprint in openSprints() AND resolution = Unresolved

sprint in openSprints() filters issues in the current active sprint.

resolution = Unresolved ensures that only issues that are still open (i.e., not resolved) are included.


This will return all issues in the active sprint that are still open (i.e., have not been resolved yet).

777777.7.777

1. Git Commit:

To add changes to a file and commit them with a descriptive message, you can follow these steps:

1. Stage the file: Use the git add command to stage the modified file. If you want to stage a specific file:

git add <file-name>

Or, if you want to add all changed files:

git add .


2. Commit the changes: After staging the changes, commit them with a descriptive message:

git commit -m "Your descriptive commit message"



This sequence stages the changes and commits them to the local repository with a message describing the modifications.


---

2. Git Pull:

To pull the latest changes from the main branch into your current branch without conflicts:

1. Fetch the latest changes: First, make sure you have the latest data from the remote repository:

git fetch


2. Pull the changes from main: Assuming your teammate pushed updates to the main branch, you can pull them into your current branch (let's say you're working on a feature branch) using:

git pull origin main

Git will attempt to merge the changes from the main branch into your current branch. If there are no conflicts, it will merge automatically. If there are conflicts, Git will prompt you to resolve them manually.

If conflicts occur:

1. Resolve the conflicts in the affected files.


2. After resolving, mark them as resolved:

git add <file-with-conflict>


3. Complete the merge by committing:

git commit -m "Resolved merge conflicts"







---

3. Jira Board Configuration (Kanban Board for Bug Tracking):

To configure a Kanban board in Jira and customize its columns for bug tracking:

1. Create or Modify a Kanban Board:

Go to Jira Software and select your project.

Navigate to the Board section (on the sidebar).

If you need to create a new board, click Create Board, then choose Kanban. If modifying an existing board, click on the board settings.

Choose Kanban as the board type if creating a new board.

Set the project or filter that the board should display.



2. Customize Columns:

Once the Kanban board is set up, go to the Board Settings by clicking the ellipsis (three dots) in the top-right corner of the board and selecting Board Settings.

Under Columns, you can customize the columns. Jira will typically have columns like To Do, In Progress, and Done, but you can modify them to suit your team’s workflow:

Add a column: Click Add Column to add a new column for specific statuses.

Rename columns: You can edit the names of existing columns to reflect your process better.

Assign status to columns: Jira allows you to map Jira issue statuses (e.g., "Open", "In Progress", "Resolved") to these columns. Customize the columns to show the appropriate statuses.

Set WIP (Work In Progress) limits: You can limit how many issues can be in a column at any time (for example, a limit on "In Progress" issues).




3. Save Changes: After configuring the columns, save your changes, and your Kanban board will reflect the new layout for tracking bugs or any issues.







