# Git basic

## Get clone from GitHub
```bash
git clone <"SSH link">
```

## How to create file using terminal
```bash
echo "what to put in the file" >> file.md
```

## How to push on git
```bash
git add . #. means all files, can be replaced with file name
git commit -m "A message describing what you have done to make this snapshot different"
```

## Check current status and commit history
```bash 
git status
git log #give you all details of all commit - press 'q' to quit
git log --oneline #only show each past commits as one line
```

## COMMIT

### Commit with a **subject and body** in the message
Subject: summary of the change 
Body: A concise yet clear description of what you did.
[more to this](https://www.theodinproject.com/lessons/foundations-commit-messages)

To do that commit without the `-m` flag and message argument
```bash
git config --global core.editor "code --wait" # use this code prior to avoid getting stuck at Vim
git commit
```

### Make changes to previous commit
`git commit --amend` allows you to amend the **previous commit** with the files that you've added

>[!CAUTION]
> Avoid editing directly on GitHub
use the following code to remove file if needed
>```bash
>git rm .\filename
>```

# Branch [:link:](https://www.theodinproject.com/lessons/foundations-revisiting-rock-paper-scissors)
```bash
git branch <branch_name> # create new branches
git checkout <branch_name> # change to the new branch
git checkout -b <branch_name> # create and change to the new branch in one line

git branch # see all the current branches

git merge <branch_name> # once finished working on the feature branch
# merge the feature branch to the main branch

# to delete branches
git branch -d <branch_name> # if the branch has already been merged into main
git branch -D <branch_name> if it hasn’t
```