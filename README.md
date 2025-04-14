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






