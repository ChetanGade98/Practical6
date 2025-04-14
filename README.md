# Practical6
Here are the detailed answers to both questions:

Q1. Git Scenario - Project Initialization

Scenario: You're starting a new project called invoiceApp.

Steps with Git Commands:

1. Initialize Git in the project folder:



mkdir invoiceApp
cd invoiceApp
git init

2. Create a remote GitHub repo:



Go to GitHub and create a new repository named invoiceApp (do not initialize with a README).


3. Connect the local repo with the remote GitHub repo:



git remote add origin https://github.com/your-username/invoiceApp.git

(Replace your-username with your actual GitHub username.)

4. Add all files, commit, and push to the main branch:



git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main

Q2. JQL Advanced Search - Created, Due, and Resolution Filters

a. Find all issues created in the last 10 days that are still unresolved

created >= -10d AND resolution = EMPTY

created >= -10d: Created in the last 10 days

resolution = EMPTY: The issue has not been resolved

b. Show all issues that are due in the next 3 days

due <= 3d

due <= 3d: Due date is within the next 3 days

c. Find all bugs that were resolved in the last 5 days

issuetype = Bug AND resolved >= -5d

issuetype = Bug: Filters only bugs

resolved >= -5d: Resolved in the last 5 days


Explanation: resolution = EMPTY vs status != Done
resolution = EMPTY: Checks if the resolution field is blank, which means the issue hasn’t been marked as resolved. This is a field-level check.
status != Done: Checks if the issue status is not equal to "Done". This is a workflow/status-level check.
Key Difference:
An issue might be in "Done" status but still have resolution = EMPTY (if not set correctly).
resolution = EMPTY is more accurate when filtering for unresolved issues.


Set 2

Here are the detailed answers to both questions:

Q1. GitHub Scenario – Team Collaboration

Steps:

1. Create a new GitHub repository
Go to GitHub
Click New Repository
Name it (e.g., team-project)
Select "Add a README.md"
Click Create repository

2. Add a README.md
(Already done during creation step. If skipped initially:)
Click Add file > Create new file
Name it README.md, add content, and commit it

3. Invite your team for collaboration
Go to your repo → Click Settings > Collaborators
Add your teammates by GitHub username or email
Send the invite and wait for them to accept

4. Set up branch protection on main to require pull requests
Go to Settings > Branches > Add rule
Under “Branch name pattern”, type: main

Check:
Require pull request reviews before merging
(Optional) Require status checks to pass


Save the rule

Q2. JQL Search – Transitions, Assignee, Due Dates

a. Find issues where status changed from "To Do" to "In Progress" in the last 7 days
status CHANGED FROM "To Do" TO "In Progress" AFTER -7d
Shows all issues that transitioned from To Do to In Progress within the last 7 days.

b. List all issues assigned to you that are overdue
assignee = currentUser() AND due < now()
currentUser() picks the logged-in user
due < now() means the due date has passed (overdue)

c. Show all tasks that transitioned to "Done" in the last 2 days

issuetype = Task AND status CHANGED TO "Done" AFTER -2d
Filters only tasks
Finds those that moved to Done in the last 2 days

Explanation: CHANGED Keyword in JQL
The CHANGED keyword tracks workflow transitions over time.
It helps answer "when" and "how" issues changed state.

Example Use Cases:
Track how long issues stay in each status
identify workflow bottlenecks
Build automation rules based on transitions

Set 3











