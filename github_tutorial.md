#Git / GitHub: How to use it?

#### What is git?
 - version control and git
 - Storing snapshots of text at a given period of time
 - Can switch back and forth between files in a given point in time
 - Instantiated wherever .git file is present. Possibility to have different folders containing different .git files corresponding to different repositories.
 - Generally thought of as a “tree”, with the “master” branch as the “trunk” and “branches” of specific feature works stem from the trunk but can go in different directions

**Image 1**: Simple Workflow

https://cloud.githubusercontent.com/assets/3063909/13062787/fba25682-d40e-11e5-8993-29a8ae08c5d3.png

 - Master branch is the main source of truth and stable set of codebase.
 - Features or changes to the codebase are made on branches. Developer will create separate branch off of main branch at a given point in time.
 - At the same time another developers branch might be ready and merged back into the main master branch thereby changing the codebase from what the previous developer had "copied".
 - At the point in time (the later point), another developer may branch a different change.
 - If these changes are both accepted, they both need to go back into the main master branch. Git allows for merging and compiling to resolve line changes and align conflicting changes.

**Image 2**: GitFlow Workflow

https://cloud.githubusercontent.com/assets/3063909/13062786/fba183ba-d40e-11e5-8bc6-10c48eba84bf.png

 - SHA: unique on 6 first characters
 - While version control is generally thought of as a straight line, or a tree, it is a "point" (represented by a SHA or any unique identifier) that represents the entire set of files at a given time. The unique identifier is created by a "commit". In general, the workflow is:
     - You have a bug or a feature you want to work on. Say, Adding a commenting system to a blog article.
     - For this feature, you create a branch off of master, but within that branch you will make several changes.
     - For example: Add the form for the comment box, Style the form, Add the backend functionality for posting the form, etc.
     - After you make each of these changes, you would "commit" your changes. Each commit creates a SHA and that SHA represents the  entire file set at that point.

#### Lets's get started
###### Navigating using command line:
 - Using Command line to navigate to particular folder
 - Basic unix commands:
     - create directory: `mkdir directory_name`
     - view file: nano `file_name.txt`
     - view list: `ls`
     - change directories: `cd directory_name`
     - change to previous directory: `cd ..`
     - overwrite as root: `sudo` (We stay away from this as much as possible because we would rather be the “user” and not the “root”)

###### Download Text Editor:
While we could do all of our editing in nano, emacs, vim or any command line editor, it is visually easier to use an IDE (GUI text editor), such as Sublime or Atom.

###### Setup Git
 - Difference between Git and Github: git is a command line tool that manages the version control system. Github is a storage system to hold the actual files and change sets. It also has several features to help visualize version control changes.
 - Install git on machine
     - `apt-get install git`
     - `brew install git`

###### Using GitHub to manage
 - Create GitHub account
 - Create a repo in Github
 - Create Folder for all your github repositories
 - Clone repo onto your local machine: `git clone ...`

###### GitX / GitK / Similar Visualization
 - Visualize log
 - Visualize where you are relative to previous commits

###### Flow of using Git Individually:
 - `cd` into directory of cloned repository
 - `git branch`: Shows you the branches available and the branch on which you are located
 - `git checkout -b new_branch_name`: From the branch where you are now, check you out on a different branch, the new branch name
 - `git checkout -B` vs `git checkout -b`
 - Open file in Sublime, make changes
 - Save files to computer in the folder of the repo
 - `git status`: Shows uncommitted and staged changes
 - `git add .`: Add file/changes  to be tracked/ staged so they are now recognized by git.
 - `git commit`, `git commit -am`: Commit those changes to be stored as a snapshot
 - Message for that specific staged change. Good Practices include being as specific as possible, starting with active verb, ex: "Adds print statement to track progress"
 - It will prompt a message.
     - To write in VIM : press i
     - When done typing press escape, VIM editor closes
     - `shift colon` then type `wq` which exists out of VIM and sends your message
 - Check gitx to see that commit is correct and changes are ok
 - `git push origin new_branch_name`:  Push those changes to origin/new_branch_name
 - Repeat

Notice how when working alone, you might rarely ever create a branch because you might be working directly on master. Branches are to keep features separate in the same repo so you can work on two things simultaneously without them breaking one another .


###### Flow of using Git Collaboratively:
 - Open Source collaboration
 - Creating Pull Requests on repositories where there is another owner
 - Benefits / Requirements around code collaboration in a career setting
 - `git fetch`: Fetch the latest changes from the origin

Merging vs Rebasing
 - `git merge`: Merge in changes into your branch
 - `git rebase`: Rebase your commits on top of other commits
 - In both cases, you will need to resolve conflicts, if the changes on your branch conflict with changes outside.


###### Ready for Final Merge to Master?
 - Ask yourself:
     - Have you taken all the latest changes from origin master?
     - Have you taken all the latest changes from others working on that branch?
 - `git checkout master`
 - Fast forward merge vs Non-Fast forward merge
 - `git merge --ff-only branch_to_which_you_want_to_fast_foward`
 - `git merge --no-ff branch_to_which_you_want_to_merge`
 - `git push origin master`


#### Helpful Links and Blogs:
 - Git Overall: https://www.atlassian.com/git/tutorials/
 - Git FAQ: http://firstaidgit.io/
 - Undo anything: https://github.com/blog/2019-how-to-undo-almost-anything-with-git
 - Pretty good tutorial: http://gitimmersion.com/index.html
 - Cheatsheet: http://cheat.errtheblog.com/s/git
 - Interactive cheatsheet: http://www.ndpsoftware.com/git-cheatsheet.html
 - GitHub's learning tool: https://try.github.io/
 - Pretty in-depth interactive tutorial, with challenges: http://pcottle.github.io/learnGitBranching/
 - Git & GitHub secrets: https://zachholman.com/talk/git-github-secrets/
 - GitHub Pages: https://pages.github.com/

Thank you @marcypetro and @chrisjlebron


###### Exact commands for Stern Presentation
- `cd Desktop`
- `mkdir git_folders`
- If you have homebrew installed then do the following
  - `brew install git`
- If not, install homebrew first:
 - `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

 - Put in password for sudo computer
 - `cd git_folders`
 - `brew install git`
 - go to github.com
 - Create account
 - `git clone name_of_cloned_folder`
 - If going via command line, need to sync ssh keys. Follow directions on github
 to add a public ssh key so computer detected is acceptable.
   - `cd name_of_cloned_folder`
   - Check branches available by typing `git branch`
   - Create a new branch on which to work: `git checkout -b new_my_name_branch`
   - Open text editor, create new .md file and type something in it. Save the file in the name_of_cloned_folder.
   - Then open gitx, gitk, Github Desktop and visualize changes made
   - `git add new_file_name`
   - `git commit -m 'commit message'`
   - `git push origin new_my_name_branch` If you have permissions to merge this to master as collaborator
 - Else go through Github Desktop
