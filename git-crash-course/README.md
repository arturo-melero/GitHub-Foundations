## Git Hidden Folder

There is a hidden folder called `.git` which tells you that our project is a git repo.

If you want to create a git repo in a new project, we need to create the folder and then initialize that repo using `git init`

## Cloning

We can clone three ways: HTTPS, SSH and GitHub CLI.

Since we are using GitHub Codespaces we'll create a temporary directory in our workspace.

```sh
mkdir /workspaces/GitHub-Foundations/new-project
cd /workspaces/GitHub-Foundations/new-project
git init
touch readme.md
open readme.md
git status
git add readme.md
# makes changes to readme.md
git commit -a -m "add readme file"
```

### HTTPS

```sh
git clone https://github.com/arturo-melero/GitHub-Foundations.git
cd GitHub-Foundations
```

> You'll need to generate a Personal Access Token (PAT):
https://github.com/settings/tokens

You will use the PAT as your password when you login

### SSH

```ssh
git clone git@github.com:arturo-melero/GitHub-Foundations.git
cd GitHub-Foundations
```

### GitHub CLI

Install the CLI according to your SO. You can follow the guideline in `https://cli.github.com/`. Once done:
```sh
gh auth login
gh repo clone https://github.com/arturo-melero
```

## Commits

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit
```

Set the global editor.
```
git config --global core.editor emacs
```

Make a commit and commit message without opening an editor.
```sh
git commit -m "add another exclamation"
```

## Branches

List of branches
```
git branch
```

Create a new branch
```
git branch branch-name
```

Checkout the branch
```
git checkout branch-name
```

## Remotes

We can add remote, but often you will just add remote via upstream when adding a branch.

```sh
git remote add ...
git branch -u origin new-feature
```

## Stashing

```sh
git stash list
git stash
git stash save my-name
git stash apply
git stash pop
```


## Merging

```sh
git checkout dev
git merge main
```

## Add

When we want to stage changes that will be included in the commit we can use the period (.) to add all possible files.

```
git add readme.md
git add .
```

## Reset

Reset allows you to move Staged changes to be Unstaged.
This is usefull when you want to revert all files not t be commited.

```
git add .
git reset
```
> git reset will revert a git add .

## Status

Git status shows you what files will or will not be commited.

```
git status
```

The gitconfig file is what stores your global configurations for git such as email, name, editor and more.

Showing the contents of our .gitconfig file.
```
git config --list
```

When you first install Git on a machine you are supposed to setup your name and email:

```sh
git config --global user.name "Arturo Melero"
git config --global user.email arturom@example.com
```

We will need to create our own SSH rsa key pair

```sh
ssh-keygen -t rsa
```

For WSL users and if you create a non default key you might need to add it.

```sh
eval `ssh-agent`
ssh-add /home/.../name
```

We can test our connection here:
```
ssh -T git@github.com
```

## Log

`git log` will show recent git commits to the git tree

## Push

When we want to push a repo to our remote origin

```
git push
```