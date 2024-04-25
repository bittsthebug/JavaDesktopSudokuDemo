## Git hidden folder

There is a hidden folder called `.git` which tells you that your project is a git repo.

If we wanted to create a git repo in a new project we'll create the folder and then initialize that repo using `git init`
```
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add Readme.md
# makes changes to Readme.md
git commit -a -m "add readme file"
```

## cloning 
we can clone three ways - HTTPS, SSH, GITHUB CLI

since we are using Github Codespaces we'll create a temporary directory in our codespaces 

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS
```sh 
git clone https://github.com/bittsthebug/JavaDesktopSudokuDemo.git 
cd JavaDesktopSudokuDemo
```
> you'll need to generate a personal access token (PAT)
https://github.com/settings/token

you will use the PAT as your password when you login

- Give it access to contents for commits 

### SSH
``` ssh
git clone git@github.com:bittsthebug/JavaDesktopSudokuDemo.git
cd JavaDesktopSudokuDemo
```
we will need to create our own SSH rsa key pair 

```sh 
sshe-keygen -t rsa
```

for WSL users and if you create a non default key you might need to add it
```sh 
eval `ssh-agent`
 ssh-add /mnt/c/Users/Vaishali/.ssh/alt-github_id_rsa
```

we can test our connection here:
```

ssh -T git@github.com
```

### Github CLI 

Install the CLI 

eg. Linux(Ubuntu)
```sh 
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
&& sudo mkdir -p -m 755 /etc/apt/keyrings \
&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

```
gh auth login
gh repo clone bittsthebug/JavaDesktopSudokuDemo
```


## commits 

when we want to commit code we can write git commit which will open up the commit message in the editor of choice.

```sh
git commit
```

Set the global editor 
```
git config --global core.editor emacs
```
Make a commit and commit message without opening an editor

```sh
 git commit -m "add another exclamation"
 ```

## branching

List of Branches 

```
git brach
```

Create a new Branch 
```
git branch branch-name
```

Checkout the branch

```
git checkout dev
```



## remotes 

## tashing

## merging

## Add 
 when we want to stage changes that will be included in the commit , we can use the `.` to add all possible files.
```
git add Readme.md
git add . 
```

## reset

Reset allows you to move staged changes to unstaged .
This is when you want to revert all files not to be not commited 

```
git add . 
git reset
```

> git reset will revert a git add .

## status 

git status will show you what files will or will not be commited .

```
git status 
```

## gitconfig file
 The gitconfig file is what stores your global configurations for git such as email , name , editor and more.

showing the contents of our .gitconfig file
 ```
 git config --list
 ```

 when you first install git on a machine you are supposed to set up your name and email

 ```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## log 

git log will show recent git commits to the git tree

## push

when we want to push a repo to our remote origin

```
git push
```