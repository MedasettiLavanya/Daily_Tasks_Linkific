Git, Github & Test Documentation.

By using Git (the tool) and GitHub (the hosting service), you are creating a professional "Audit Trail" for your test artifacts.

As a tester, you use Git to track changes in your test plans, automated scripts, and bug reports.

Git for testers

What is Git ?
Version control system for tracking changes in computer files.

Version control system : it is a system changes that records every changes made to a files or set files over time so that you can recall specific versions later.
 
It allows multiple testers to work on the same document at the same time without overwriting each other's work.
 
Distribute version control
Coordinates work between multiple developers/ tester 
Who made what changes and when
Revert back at any time
Push to local and remote repos.

Concepts of GIT.

Keeps track of code history
Take “snaphots” of your files
You decide when o take a snapshots by making a “commit”
You can visit any snapshot at any time
You can stage files before committing.

Basic commands

git init ( starter): this turns and ordinary file into a Git repository. Only once at very beginning of project.
          It creates a hidden folder called .git that starts tracking every change you make.
git status ( the checker): Its is the most used command. Use it constantly befor and after other commands
           It tells you which files have been changed, which are "staged," and which haven't  been saved yet.
3.git add <filename>  (The stage) : Beffor you save a ‘snapshot” you have to put files on th e”stage.” When you finish editing testcase or artifacts.
Shortcut: Use git add. To stage every changed file in your folder at once.

4. Git commit -m “Message” ( The snapshot) : this saves your changes to the local history on your computer.
When to use it: Every time you reach a milestone( ex: “ Finished 30 Registration cases”);
Tip: always write a clear message in the quotes 

5. git push( the sync) : this takes all the snapshots( commits ) from your computer and uploads them to GitHub.
When you want your team to see your work online.

6. git clone ( The one- time setup): you use this when you want to copy a repository from github onto your computer for the first time.
It create a new folder, downloads every files, and set up the entire version history.
When you start a new job and need the teams existing test cases, or when you want to move your work to different laptop
The Command: git clone https://github.com/username/repository.git


7.git pull( the daily update):   You use this when you already have the folder on your computer , but someone else has added new work to github.
It checks github for any new commits and merges them into you local files .
Every morning before you start testing to make sure you have the latest version of the test documentation.
The Command: git pull origin main.

8.gitignore : When testing, you'll often have files you don't want to save in Git (like temporary Excel files, local logs, or system folders).
A .gitignore file is a simple text file where you list the names or patterns of files Git should ignore. It acts like a filter for your filing cabinet.
For example, a .gitignore for test artifacts 


Git basics for testers ( for artifacts)
Stage 1: Starting Your Project
These commands are used to get a project onto your computer.
git init: This starts a brand new, empty repository (repo) on your local machine. It’s like buying a new filing cabinet for a project that doesn't exist yet.
git clone: This copies an existing project from a server (like GitHub) to your computer. It’s like taking a full photocopy of someone else's filing cabinet so you have your own identical copy to work on.
Stage 2: Saving Your Progress
   3.git add: Putting a document in an "Outbox"Moves your    changes       to a Staging Area. Git now knows you want to save these specific files.
     4.git commit: Taking a permanent photo of the Outbox .Saves a "snapshot" of the staged files to your local history. You must add a message (e.g., "Added 30 login cases").
     5.git push: Sending the photo to the Head OfficeUploads your local commits to the remote server (GitHub) so others can see them.
 Stage 3: Staying Synced
6.git fetch: This tells your computer to check the server for updates, but it doesn't change your files yet. It’s like checking the tracking number on a package to see where it is.
7.git pull: This is a combination of fetch and merge. It downloads the new data and immediately updates your local files. It’s like the package arriving and someone putting the contents directly onto your desk.

8..gitignore File
When testing, you'll often have files you don't want to save in Git (like temporary Excel files, local logs, or system folders).
A .gitignore file is a simple text file where you list the names or patterns of files Git should ignore. It acts like a filter for your filing cabinet.

Commit message conventions :
 Commit message conventions are a set of rules that developers and testers follow to keep the project history organized and readable.
Professional teams use a standard called Conventional Commits. This makes it easy to see at a glance what changed without opening the files.
The Standard Format
A good commit message usually follows this structure: <type>: <description>
Type: A short prefix telling us what kind of change it is.
Description: A brief, present-tense statement of what was done.


Type
When to use it
Example
test
Adding or updating test cases/scripts.
test: add 10 negative cases for login
docs
Updating the Test Plan, RTM, or README.
docs: update RTM for registration module
feat
(Mainly for devs) Adding a new feature.
feat: implement show password toggle
fix
(Mainly for devs) Fixing a bug.
fix: resolve email validation regex error
chore
Maintenance tasks (updating .gitignore).
chore: add excel temp files to gitignore


 10+ Examples for Test Artifacts
use "Add" or "Update" instead of "Added" or "Updated."
docs: create initial test plan for registration module 
test: add 15 positive test cases for user login 
test: add 10 negative test cases for email validation 
docs: map requirements to test cases in RTM 
chore: add .gitignore to exclude temporary excel files 
test: add boundary value analysis cases for password field 
test: add security-focused cases for SQL injection 
docs: update README with project setup instructions 
test: add usability cases for password masking 
test: add 5 edge cases for security question dropdown 
docs: finalize test summary report for sprint 1 


Type
Purpose
Content Type
test
Testing logic/steps
Test Cases, Automation Scripts
docs
Explanatory info
README, Test Plan, RTM
chore
Maintenance( like cleaning garbage 
.gitignore, Folder moves, Configs

Branching for Testing
Branching is how we organize different versions of our work so they don't get messy. Imagine your main project folder is a "Master Document". Instead of everyone editing that one file at once, Git lets you create "copies" or Branches  to work on specific tasks safely.
Branch Types
feature/test-login: The feature/ prefix tells the team you are working on something new. In this case, you are writing the test cases specifically for the Login functionality.
bugfix/login-validation: The bugfix/ prefix tells the team you found a mistake in existing tests (like a typo or a wrong step) and you are fixing it.
The Workflow
Create branch for each feature: You never work directly on the "Main" branch. If you are starting "Registration" tests, you create a new branch called feature/test-registration. This keeps your work isolated.
Merge after review: Once you finish your 80 test cases on your branch, a Senior Tester reviews them. If they look good, your branch is "Merged" (combined) back into the Main project folder.



After installation of Git
Set up a username and email id
And create git repository 






why do we need a git repository 
We need to convert a plan directory to a git directory to use git commands.
Create normal folder in c drive 

