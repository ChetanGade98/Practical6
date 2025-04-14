# Practical6

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

Q1. Git Scenario – Branching & Pull Request (PR)
Scenario: You're working on a new search feature in a shared GitHub project.

Steps:

1. Create a new branch named search-feature
git checkout -b search-feature

2. Make your changes and push the branch to GitHub
git add .
git commit -m "Added search feature"
git push origin search-feature

3. Open a Pull Request (PR) on GitHub
Go to the repo on GitHub
You'll see a prompt to open a PR for the search-feature branch
Click "Compare & pull request"
Add title and description of the feature
Assign a reviewer from your team (right sidebar in PR window)

4. Merge the PR after review is approved
Once the reviewer approves the PR
Click "Merge pull request"
Optionally delete the branch after merging

Q2. JQL – Created, Updated & Transitioned Filter Queries
a. Issues created between March 1 and March 10, 2025
created >= "2025-03-01" AND created <= "2025-03-10"
b. Issues updated within the last 3 days
updated >= -3d

c. Issues that transitioned from "In Progress" to "Testing" after April 1, 2025
status CHANGED FROM "In Progress" TO "Testing" AFTER "2025-04-01"
Difference: updated >= -3d vs created >= -3d
Tip: Use updated for tracking activity or progress, and created to identify recent backlog entries or incoming tasks.

Set 4

Q1. Git Scenario – Resolve Merge Conflict
Scenario: You and your teammate edited the same file in different branches. Now there's a merge conflict.
1. How to view the conflict
After trying to merge:
git merge teammate-branch
You’ll see an error like:
Auto-merging filename.js
CONFLICT (content): Merge conflict in filename.js
Automatic merge failed; fix conflicts and then commit the result.
To view conflicted files:
git status
You’ll see something like:
Unmerged paths:
  (use "git add <file>..." to mark resolution)
	both modified:   filename.js
In the file itself, conflicts are marked like this:
<<<<<<< HEAD
Your changes in current branch
=======
Teammate’s changes from merged branch
>>>>>>> teammate-branch


2. How to resolve it locally
Open the conflicted file in a text editor or IDE
Manually choose which changes to keep (or combine both)
Remove the conflict markers (<<<<<<<, =======, >>>>>>>)
After resolving:
git add filename.js

3. How to commit and complete the merge
git commit -m "Resolved merge conflict in filename.js"
Now the merge is complete. You can push the result:
git push

Q2. JQL – Component, Labels, and Sprint Filters

a. Find all issues in the Frontend component that are unresolved
component = Frontend AND resolution = EMPTY


b. List issues labeled as urgent or production-fix
labels in (urgent, production-fix)

c. Show all issues in the current sprint and assigned to your team
sprint in openSprints() AND team = "Your Team Name"
(If team is not a custom field in your JIRA setup, use a group of assignees instead.)
Alternatively:
sprint in openSprints() AND assignee in membersOf("your-team-group")

Labels vs Components – When to Use What
Use labels when:
You want to quickly tag cross-cutting concerns or priorities
You need ad-hoc filters (like bugfix, QA-needed, hotfix)

Use components when:
You want to assign ownership to teams/modules
You want structured, consistent categorization

Set 5

Q1. GitHub Scenario – Team Collaboration

Steps to follow when working on a group project:

1. Create a new GitHub repository:
Go to GitHub
Click "New repository"

Fill in:
Repository name (e.g., group-project)
Set visibility (public/private)
Check “Add a README file”
Click "Create repository"

2. Add a README.md
(If skipped during creation):
Go to the repo → Click "Add file" > "Create new file"
Name it README.md, add initial content
Commit the file to the main branch

3. Invite your team for collaboration:
Go to the repo → Settings > Collaborators
Click “Invite a collaborator”
Enter their GitHub username or email
They will receive an invite to accept

4. Set up branch protection on main to require pull requests:

Go to Settings > Branches > Add rule
Under "Branch name pattern", type: main
Enable:
Require pull request reviews before merging
(Optional) Require status checks to pass before merging
Click Create or Save changes

Q2. JQL – Release Readiness Queries

a. Find all issues targeted for fixVersion = "v2.0"
fixVersion = "v2.0"

b. List bugs in v2.0 that are still unresolved
fixVersion = "v2.0" AND issuetype = Bug AND resolution = EMPTY

c. Find tasks in v2.0 that were resolved in the last 7 days
fixVersion = "v2.0" AND issuetype = Task AND resolved >= -7d

Why fixVersion is useful for managing product releases
The fixVersion field in Jira helps you organize and track which issues are planned for or completed in a specific product release version.

Benefits:
Release Planning: Helps teams plan which features/bugs go into each release (e.g., v2.0, v2.1)
Progress Tracking: Shows what’s done vs pending for that version
Release Notes: Jira can generate release notes based on fixVersion
Clarity: Keeps the team aligned on what’s ready for production and what’s not
In short: fixVersion links issues directly to product versions, making it essential for structured, reliable releases.


Set 6

Q1. Git Scenario – Tag and Release
You're ready to release version 1.0. Here’s how you can do it:

1. Tag the release as v1.0
You can create a tag using the following command:
git tag -a v1.0 -m "Release version 1.0"
This creates an annotated tag named v1.0 with a message describing the release.

2. Push the tag to GitHub
Once the tag is created, push it to the remote GitHub repository using:
git push origin v1.0
This makes the tag available on GitHub.

3. Create a release on GitHub from the tag

Steps:
Go to your GitHub repository in a browser.
Click on “Releases” (usually on the right sidebar or under “Code”).
Click “Draft a new release.”
In the “Tag version” dropdown, select the v1.0 tag you created.
Add a title and description (e.g., "Initial stable release").
Click “Publish release.”
This links the tag to a release page, useful for versioning and distributing binaries or source code.

Q2. JQL – Overdue & SLA Queries
Assuming you're using Jira Service Management with SLA fields enabled:

a. Show all issues that are overdue by more than 2 days
due <= -2d
Explanation: Shows all issues with a due date at least 2 days in the past (i.e., overdue).

b. List all issues that must be resolved within 48 hours
If you have an SLA called “Time to resolution”, the query would be:
"SLA Name" = "Time to resolution" AND "Time to resolution" <= remaining("48h")
If you're using a custom field or label:
labels = sla_48hr OR "Custom SLA Field" <= 48h
(Replace "Custom SLA Field" with the actual field name.)

c. Find issues with a due date within this week
due >= startOfWeek() AND due <= endOfWeek()
This filters issues that are due anytime during the current calendar week.

How JQL Helps with SLA Enforcement

JQL (Jira Query Language) enables teams to:
Track SLA metrics by querying issues approaching or breaching SLAs.
Automate alerts for SLA breaches using filters + automation rules.
Prioritize tickets based on time left to resolve or response deadlines.
Generate reports and dashboards to monitor performance against SLAs.
Ensure accountability by identifying overdue tickets and bottlenecks.
In service-based teams, this improves response times, customer satisfaction, and operational transparency.


Set 7

Q1. Jira Scenario – Scrum Project Setup
1. Create the Project

Go to Jira, click on “Projects” > “Create project”.
Choose the Scrum template (under Software Development).
Name your project (e.g., “My Scrum Project”) and set a key.
Select either a Team-managed or Company-managed project (Team-managed is simpler for small teams).
Click “Create”.

2. Set up a Board and Sprints
A Scrum board is automatically created with the project.
Go to the “Backlog” tab.
Click “Create Sprint” to prepare your first sprint.

3. Add Backlog Items
In the backlog, click “Create issue” to add user stories, tasks, or bugs.

Example:
Story: "As a user, I want to reset my password"
Task: "Design login UI"
Drag issues into the sprint section to plan your upcoming sprint.

4. Start and Manage a Sprint
Click “Start Sprint” on the sprint section.
Set a name, start date, end date, and duration (typically 2 weeks).
Once started, manage tasks on the board through stages like To Do, In Progress, and Done.
At the end, click “Complete Sprint” — unresolved issues can be moved to the next sprint or back to the backlog.

Q2. JQL – Team Assignment and Status Filters
a. Find all unresolved tasks assigned to Team-A
assignee in membersOf("Team-A") AND resolution = Unresolved AND issuetype = Task
This lists all tasks assigned to Team-A that are not yet resolved.

b. Find issues currently in "Blocked" status for more than 2 days
status = Blocked AND status changed TO Blocked BEFORE -2d
This helps identify items that have been in the "Blocked" status for over 2 days.

c. List all bugs assigned to your name and in "In Review"
assignee = currentUser() AND status = "In Review" AND issuetype = Bug
This shows all bugs currently in the “In Review” status and assigned to you.
Why Team-Level JQL Filters Are Valuable on Sprint Dashboards
Improved visibility: Teams see only their relevant tasks and progress.
Focused work: Filters eliminate distractions by excluding unrelated work items.
Accountability: Helps managers and team leads monitor each team’s workload.
Sprint progress tracking: Teams can quickly spot delays or blockers.
Custom automation and alerts: Filters power dashboards, SLA monitoring, and notifications.

Example: A filter like
status = Blocked AND assignee in membersOf("Team-A")
on a dashboard ensures Team-A sees and resolves blockers quickly.


Set 8





