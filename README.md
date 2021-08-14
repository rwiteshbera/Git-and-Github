## Git and Github
 Git is a version control system that allow us to collaborate with other developers. It helps a person to store, manage code and keep tracking changes made in the codebase of a project they are working on.

Github is a web-base platform for code hosting. It helps you to work together with other people on various projects.

### How to install Git
You can download and install **Git** from the official website. 
Download Link: [https://git-scm.com/downloads](https://git-scm.com/downloads)

In Linux, you can install latest version of Git by using the following command.
```
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt-get install git
```

After installation is done, you can check the version by using this command.
```
git --versoin
```
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

#### Return to old Git commit
```
git checkout <hash id>
```
It will return to a old commit and change the files to that specific commit.
