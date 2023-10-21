
# Git and Github
 Git is a version control system that allow us to collaborate with other developers. It helps a person to store, manage code and keep tracking changes made in the codebase of a project they are working on.

Github is a web-base platform for code hosting. It helps you to work together with other people on various projects.

### How to install Git
You can download and install **Git** from the official website. 
Download Link: [https://git-scm.com/downloads](https://git-scm.com/downloads)

After installation is done, you can check the version by using this command.
```
git --version
```
### Configure Git with Github 
**Add GitHub username and email**
```
git config --global user.name "rwiteshbera"
git config --global user.email "rwiteshbera@gmail.com"
```

**Add a new SSH key to your GitHub account**
1. **Generate new SSH Key:**
```bash
ssh-keygen -t ed25519 -C "rwiteshbera@gmail.com"
```
2. **Start the SSH agent:**
```bash
 eval "$(ssh-agent -s)"
```
3. **Add SSH key to agent:**
```bash
ssh-add ~/.ssh/id_ed25519
```
4. **Copy the SSH key to clipboard:**
```bash
cat ~/.ssh/id_ed25519.pub
```
5. **Add the SSH key to your GitHub account:** 
-   Go to your GitHub account settings.
-   Click on **SSH and GPG keys**.
-   Click **New SSH Key**.
-   Paste the SSH key you copied from the clipboard into the provided field.
-   Give your SSH key a descriptive title (e.g., "My Local Machine").
-   Click **Add SSH Key** to save it to your GitHub account.

Your Git configuration is now set up to work with your GitHub account, and you have added an SSH key for secure access.

____
### Commonly Used Git Commands

#### Initialize an empty Git repository
```
git init
```
This command will create a hidden subdirectory `.git`
After initializing Git, any changes made in the project can be tracked.

#### Inspect a repository
```
git status
```
It is used to display the state of a repository and staging area. It helps us to see the tracked and untracked changes.
Staging area is like a rough space where files are not handled by git but are going to be a part of the next commit.

#### Add untracked files
```
git add .
```
This command can be performed multiple times before commit. It will stage all the new and modified files of the current directory.
You can add individual files by specifying the name of the file like `git add <file name>`

#### Git Commit
`git commit` creates a commit which is like a snapshot of the repository at a specific times. Remember that if you don't stage anything, you won't be able to commit.
```
git commit -m "<Commit Message>"
```
#### Git Log
It is used to display a history of commits that happens to a repository.
```
git log
```
#### Discard commits in Git
If you have done any commits mistakenly, you can discard those commits to moves to a different commit and unstage files. Remember that the changed files are preserved.
```
git reset <hash id>
```
1. `git reset --soft <hash id>` - It will move your HEAD to the specified commit but doesn't touch the index or working tree. It leaves all files in staging area.
2. `git reset --mixed <hash id>` - Reset the index but not the local files. Changed files are preserved but make them unstaged. 
3. `git reset --hard <hash id>` Reset the index and working tree both.

#### Return to old commit
```
git checkout <hash id>
```
It will return to a old commit and change the files to that specific commit.

### Push code in a new repository.
First Create a repository in Github by filling up the required details.
```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:rwiteshbera/Git-and-Github.git
git push -u origin main
```
#### Git Push
```
git push -u origin <branch name>
```
It will upload local repository content to a remote github repository

#### Create branch in repository
```
git branch <branch name>
```
#### Show all branches
```
git branch
```
#### Switch to another branch
```
git checkout <branch name>
```
#### Git clone
```
git clone <url of the repository>
```
It will create a copy of remote repository in your local system.
