---
layout: page
title: FAQ
permalink: /collaborative_notes/index.html
---

# Software Carpentry at UCL: Bash, Git, and Python Workshop 29-30 Jul 2026

# https://codimd.carpentries.org/2026-07-29-UCL
:::success
## :tada: Welcome!
### :calendar: 29th - 30th Jul 2026

### :link: Links
- :page_facing_up: [Workshop website](https://github-pages.arc.ucl.ac.uk/2026-07-29-UCL/)
- :page_facing_up: [Notes made during the workshop](#Notes)
- :female-teacher: :male-teacher: [Instructors and Helpers](#Staff)
- :+1:/:-1: [Feedback](#Feedback-and-Surveys)
- :bulb: [UCL Research Programming Hub (Slack)][ucl-rph-slack]: A platform to ask programming questions to the UCL research community, you can join using your UCL email. Anything from "How to I get started on X" to "what would people recommend for solving Y".
- [ARC Drop-in session](https://www.ucl.ac.uk/advanced-research-computing/community-events/drop-sessions)

### Exercises
- Go to [gosocrative.com][socrative] and enter room code `UCLARC` to follow along and submit answers to the exercises.

### Lesson Material
- :card_file_box: [Sample data we'll be using for Unix Shell][shell-data] - follow the link and download the `shell-lesson-data.zip` file and Unzip/extract it, save to your Desktop. 
- :card_file_box: [Sample data we'll be using for Python][python-data]- follow the link and download the `python-novice-inflammation-data.zip` file and (optionally) the `code.zip` file too.
- carpentries environment: https://raw.githubusercontent.com/carpentries/workshop-template/refs/heads/gh-pages/data/carpentries_environment.yml


:::

---

# Staff

### DAY 1:

Instructors: Marlon & David
Helpers: Tom & Yean Hoon

### DAY 2:

Instructors: James & Will
Helpers: Amanda & Zakaria

# Sign In

Add your name, and which operating system (Windows / Windows Subsytem for Linux (WSL) / Mac / Linux) you'll be using for the workshop to the list below. Each bullet point begins with a `-` character on a new line.

- _example: Will Graham, linux_
- Alif Khan, MacOS
- asmaa, windows 
- Gideon, Windows
- Kyrill Potapov, windows
- Camila, Mac
- Feni, mac
- Anwar Musah, MacOS
- Frankie, windows
- Seph, windows
- Saba Hussain Mac
- Tasmin Miah , Windows
- Joel Barnett, MacOS
- Sisi Chen, MacOS
- Zoey, Windows
- Adam, macOS
- Neha Khawaja - Windows
- Thesha, MacOS
- Agnes - Windows
- Kinga, MacOS
- Yaro, Windows 11
- Michael, Windows

- Anna Gavrilova, Windows

# Feedback and Surveys

[Pre-workshop survey][pre-survey]
[Post-workshop survey][post-survey]

# Notes (Take your notes here!)


## Day 1 - Morning - Bash
### Data Downloads

As we are using different systems, the easiest way for all of us to get the data is to do the following:

1. In the WSL terminal, run the following command to download the `.zip` file:
```bash
mkdir -p Desktop
cd Desktop
curl -O https://swcarpentry.github.io/shell-novice/data/shell-lesson-data.zip
```
2. Then, extract the folder you just downloaded by running:
```bash
unzip shell-lesson-data.zip
```
3. Confirm the folder has been extracted by running
```bash
ls -F
```
and confirming that `shell-lesson-data/` appears in the output text.


### List of useful commands

- `ls`: list files or items in folder
   Tom's favourite ls options
   ```bash
   ls -ltrah
   ```
   to list long, time ordered, reversed, all, "human" size of the files (i.e., Megabytes, Kilobytes)
- `pwd`: **p**rint **w**orking **d**irectory
- `man <command>` will provide the help of the command. Exit with pressing the letter `q`
- `<command> --help` is similar to show help when using windows.
- `cd` **c**hanges **d**irectory. `cd folder` goes into `folder` directory.
    - `cd ..` goes a directory above
    - `cd` goes to your "home". Your default directory.
    - `cd .` goes to this directory, i.e., it doesn't move anywhere.
    - In the case of `ls`, `ls` nothing and `ls .` shows the same thing. If you want to list your "home" from a different directory you'll need to type: `ls ~` as `~` is a "shortcut" for "home" (`/Users/username` in windows/mac, `/home/username` in linux)
- `mkdir <foldername>` creates a directory.
- `code filename` will open a file named `filename` in VS Code
   :::warning
   Does the command no exist?
   :apple:  Inside VS Code, press <kbd>Cmd</kbd><kbd>Shift</kbd><kbd>P</kbd> and type "shell" in the palette prompt that appears in the top. Search for "Install code in the PATH" and click on it. After authenticating and accepting the pop-up, you will be able to run `code` from the terminal.
   :frame_with_picture: Windows? Reinstall VS Code and when asked, click "add code to the PATH".
   :::
- `rm filename` - **r**e**m**oves the file. I.e., it's deleted permanently (not available from the rubbish bin anymore)
    - use `-i` to run the command **i**nteractivaly, and it will ask you whether you really want to delete the file.
- `mv filename file` - **m**o**v**es (or renames) the `filename` as `file`.
- `cp filename file` - **c**o**p**ies `filename` as `file`. 
    - if provided an existing directory as second argument will copy the file inside that directory: `cp filename backup/` makes a copy of `filename` inside the `backup/` directory.
    - To copy a directory, we need to pass the argument `-r` (as **r**ecursive). `cp -r music-directory music-backup` creates a `music-backup` directory with the same content that `music-directory`.
- `wc filename` - **w**ord **c**ounter of a file, that will give you bytes, words and lines in a file named `filename`.
    - with `-l` will give you the number of **l**ines.
- `cat filename` shows the content of a file
- `sort filename` shows the content of a file sorted
- `head -n X filename` shows the first X lines of filename
- `|` (a pipe) is used to parse the output of one command as input for the next one:
  `sort -n filename | head -n 1` will show the first line of the sorted content of filename.

### General comments
- What's the difference between git bash and VS Code terminal and WSL?
    - all of them are the "same", where you can send commands to the computer. git-bash and WSL uses a language called bash. From VS Code terminal you can choose a number of terminals, included bash and wsl.



















## Day 1 - Afternoon - Git
### `git config` Commands

At the beginning of the git session, we will run through a few setup options to get `git` working on your machine. Below is a record of all the commands:

**Remember to replace Will's details with your own!**. Use the details associated with your GitHub account, if you have one.

```bash
git config --global user.name "David PS"
git config --global user.email "ucasper@ucl.ac.uk"
git config --global core.editor "code --wait"
git config --global init.defaultBranch main
git config --global pull.rebase false
```

**Only run one of the following commands, depending on your operating system**. WSL users: you count as Linux.

```bash
git config --global core.autocrlf input # linux/mac/WSL
git config --global core.autocrlf true # windows (gitbash)
```

You can view the options that you've configured by running

```bash
git config --list
```

in your terminal. If you spot a mistake, simply re-run the corresponding `git config` option above, providing the correct value (which will overwrite the one currently stored).




### List of useful git commands
- `git init` initialise a repository.
- `git status` shows the status of a repository.
- `git add` puts files in the staging area and tell Git to track a file.
- `git commit` saves the staged content as a new commit in the local repository.
- `git log` show the project’s history.
- `git diff` displays differences between commits.
- `git restore` recovers old versions of files.
- `git clone` to clone someone else's repository.

### ...
## Day 2 - Python



















<!-- Links: please don't touch! -->
[workshop-website]: http://github-pages.arc.ucl.ac.uk/2026-07-29-UCL/
[ucl-rph-slack]: https://ucl-programming-hub.slack.com/
[shell-data]: https://swcarpentry.github.io/shell-novice/data/shell-lesson-data.zip
[python-data]: https://swcarpentry.github.io/python-novice-inflammation/index.html#obtain-lesson-materials
[pre-survey]: https://carpentries.typeform.com/to/wi32rS?slug=2026-07-29-UCL
[post-survey]: https://carpentries.typeform.com/to/UgVdRQ?slug=2026-07-29-UCL
[socrative]: http://gosocrative.com
