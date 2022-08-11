# README
>This is my journey for learning data structure with python. It is inevitable for me to come across this eventually and the course i selecte is the MOOC from Michigan. Please enjoy and stay with me. Happy coding.

# Table of content

- [README](#readme)
- [Table of content](#table-of-content)
- [How to use git](#how-to-use-git)
  - [What is git?](#what-is-git)
  - [Some basic command](#some-basic-command)
  - [git Architecture](#git-architecture)
  - [Reference](#reference)

# How to use git

## What is git?
`git` is a version control software. It is often confused with `github`. The difference is that `git` is the tool that handles all of this behind the scene while `github` is the user interface and hold `remote repository`.

## Some basic command
- `git clone`: get a copy of that repository on our local machine
- `git status`: what's going on in my repository
- `git push`: push my files from local machine to remote repository held by `github`


`Merge conflicts` is a problem might happen when two developer are trying to edit the same file. It is usually done manually, example snippet is shown below

```python
<<<<<<< HEAD
test_msg = "commit!+1"
=======
test_msg = "commit!-1"
>>>>>>> 41093e175ace0787d5b8ce8135e7152521d1e3e0
```


## git Architecture

The main git architecture is shown in the diagram below and it is a 2-step method consisting of `add` and `commit`. The reason why it's a 2-step method is that it is so good.

```mermaid
flowchart LR
    block1("local working direcotry")
    block2("staging area")
    block3("remote repository")
    block1 --- block2
    block2 --- block3
```

- local working direcotry (Only you can see)
- staging area (buffer area)
- remote repository (every1 can see if public)

The default name in local directory is called **master** while the name for remote repository is called **origin**

```mermaid
sequenceDiagram
    participant L as Local directory
    participant S as Staging area
    participant R as Remote repository
    L->>S: git add + git status (if green) + git commit
    S->>L: git reset
    S->>R: git push
    R->>S: git pull
```

However, when you are setting up the connection between your local direcotry and remote repository for the first time, you need to initialize with `git push -u origin master` so for the rest of the time, you just need to use `git push`.







## Reference

- [git-tech with tim](https://www.youtube.com/watch?v=DVRQoVRzMIY)
- [git-Corey schafer](https://www.youtube.com/watch?v=HVsySz-h9r4)
- [Harvard CS 50 git](https://www.youtube.com/watch?v=eulnSXkhE7I&t=53s)