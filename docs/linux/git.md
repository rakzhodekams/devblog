# Git

- Git can be used in local-servers or in public / private servers. 

- Git is a control version and it helps the developer to have more control of the applications they are developing. 

In all Linux distros, git is already installed, or if not you can install it.

```sh
# Debian based
sudo apt install git
# Gentoo based
sudo emerge -av dev-vcs/git 
```

Open new folder and initialize git with the command

```sh 
$ mkdir newFolder
$ cd newFolder
$ git init 
```

Edit Configuration file

```sh 
vim ~/.gitconfig
```

Check global configuration

```sh
username = USERNAME
email = EMAIL@MAIL.ORG
```
1. Note: Github.com doesn't accept login with password from git-command-line. Instead,  they recommend using a token. 
2. Note: You can use the token instead of your username when asked for in "git push". Paste your generated token instead
   of your username. Press enter again to continue. 

Using git

```sh
$ git diff
$ git add file
$ git commit -m "file modification messagem"
$ git pull # ensure all files from repo are synchronized
$ git push # update / upload files to repository
```

Don't forget to configure / create access token in github pages / gitlab, etc...

Install github-cli

```sh 
# install golang before continue
# debian based distro 
$ sudo apt install github-cli
# Gentoo based distro
$ sudo emerge -av github-cli
```

Login with github-cli ( gh ) 
```sh
$ gh auth login 
```

It is recommended you save your github token into some environment variable

```sh
export GH_TOKEN="alisdjasdjçasidjaçsjdaçsokdaçsd"
```

Then, in .gitconfig add the line: 

```sh
token = $GH_TOKEN
```

---

If user have private servers to use they can setup ssh-server and become a git-server. 

```sh
mkdir repository.git # Termination with .git is necessary 
cd repository.git 
git init --bare
```

Then from developer machine you want to clone that repository. 

Lets imagine your git-server machine IP is 192.168.100.100 with a user **git**. 

```sh
git clone git@192.168.100.100:/home/git/repository.git
```

Here You can configure git to use login/passwd or ssh-public-keys

