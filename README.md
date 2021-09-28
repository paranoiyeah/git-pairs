# Git pairs for your pair programming commit

Bash script for generating git commit template with co-authors

### Configuration

Edit the .git-co-authors file, put in your teammates information.

> This file is used to generate the select list, please make sure no front/tailing whitespace and no empty line within the file.

### Installation

- Move .git-co-authors to home directory

```sh
mv ./git-pairs/.git-co-authors ~
```

- Set jira borad, template and co-authors location

```sh
git config --global commit.jira TAS
git config --global commit.template ~/.gitmessage
git config --global commit.co-authors ~/.git-co-authors
```

- (MacOS/Linux) Give paris execute permission, and move it to /usr/local, create link within bin

```sh
chmod +x ./git-paris/pairs
sudo mv ./git-pairs /usr/local
sudo ls -s /usr/local/pairs /usr/local/bin/pairs
```

- (Windows) Move pairs to home directory
```sh
mv ./git-pairs/pairs ~
```

### Usage

- Call `pairs`(MacOS/Linux) in terminal 
- Call `~/pairs`(Windows) in git bash
- Use space to toggle, enter to confirm

### Behind the scene

This script will override the .gitmessage at the set path within global .gitconfig file, and you can use it for every git commit message.

### Known issues with VSCode

<b>Reason</b>: VSCode is only watching for files within the opened directory, since ideally our config sits in home directory, it will not pick up the updated .gitmessage template automatically.

<b>How to fix</b>: Empty the current auto generated template message, restart VSCode.
