
<p align="center">
    <img src="https://user-images.githubusercontent.com/62269745/174906065-7bb63e14-879a-4740-849c-0821697aeec2.png#gh-light-mode-only" width="40%">
    <img src="https://user-images.githubusercontent.com/62269745/174906068-aad23112-20fe-4ec8-877f-3ee1d9ec0a69.png#gh-dark-mode-only" width="40%">
</p>



<br>

<h1 align="center"> Git Training Personal notes </h1>
<br>

<p align="center">
  <img src="./assets/git.svg" width="15%" align="center">
  <img src="./assets/github.svg" width="15%" align="center">
  <img src="./assets/gitlab.svg" width="15%" align="center">
</p>


## 💎 Introduction

Git is used on daily basis to move information between different repositories and files, you can change the history of commits and fix any mistakes that you made before to produce more organized shared Git workflow.

## 🧊 The Four Areas of Git
`Git project stores information in 4 seprate storage areas :`
1. `Working` Area : This area contains current files and folders that you work on.

2. `Repository` Area : This area contains the entire timeline of the project, when you commit stuff it goes here.

3. `Index` Area : This area contains files and folders that are ready to be committed, e.g. stores files before you commit them.

4. `Stash` Area : This area is a temporary storage area.

## 👥 The Two Questions

`These two questions you ask about the command before using it:`
1. How does this command move information across the Four Areas?

    * > e.g. from working to stash or index, from index to Repository? etc...

2. How does the command change the repository?
    * > e.g. create a commit? new branch? delete old branch? etc...


## 🧰 Git Objects
You can access this folder by running `ls .git/`

There are different objects in Git:
1. `blob` objects: represents the content of the file on some point of history.

2. `tree` objects: represents the folders of the project. 

3. `commit` objects: represents the commits of the repository whenever one is created.
    * Each commit object points at its parent commit, and linked to a certain point of history for the files that are committed, contains trees and blobs of its own timeline.

> **Note**
> all of the objects are immutable, they can be created and deleted but never changed. 

* a `branch` is a reference to series of commits.
* a `HEAD` is a reference to the main `branch` of the commit history.

> **Warning**
> Just like linked list, if you delete a `branch` from the commit history, you will lose access to all the commits in the branch that doesn't have any link with other branches.

## 👮‍♂️ Git Commands

<h4 align="center">Git is a toolbox contains different tools and commands</h4>

> **Note** : use `help <command>`to show the decomentation of a certain command.

- `status`: returns the status of the index area to commit files into repository area, if the index has the same files as the repository area, then it'll return `nothing to commit` otherwise `Changes not staged for commit:` and logs the files names and status information under `Untracked files`.

 

* `diff`: returns the difference between the working directory and the index directory, if the index has the same files as the working directory, it doesn't log any data.
    * `diff --cached`: returns the difference between the index directory and the repository directory.
    * `diff <branch1> <branch2>`: returns the difference between the branch1 and branch2.

- `add`: copy chosen files from working area to the index area, overriding existing files.

* `commit`: update the repository directory with the latest updated files in the index directory.

- `checkout`: change the `HEAD` to another branch, and takes the data from the current commit and copy these data from the working area to the index directory.

* `rm`: remove the files from the repository directory, which gives you 2 options for removing the files:
    * `-f` to force removal both index and working directories.
    * `--cached` to remove file from index directory only. `unstaged`

- `mv`: rename file in the working directory and update it in the index directory in a single shot.

* `reset`:  revert or undo changes to the repository. It can be used to reset the repository to a specific commit, or to a specific file. The reset command can also be used to remove files from the repository.
    * `--hard`: copies the new current commit to the main working area and the index area.
    * `--mixed`: copies the new current commit to the index area. <em>Which is the default</em>
    * `--soft`: moves the branch to the new commit without effecting index nor working area.
        - `reset HEAD`: reset the staged files to the current commit in the repository.
        - `reset --hard HEAD`: reset the current files in both index and working areas to the current commit in the repository.
        > **Warning**:
        > This will reset the files in the working area.
- `stash`: save the current state of the working area and index area to a temporary area, and checks out the current commit in the repository not affected with files in the stash area.
    - `--include-untracked`: saves the current state of the working and index area.
    - `list`: lists the stash elements in the stash area. e.g. `stash@{0}`
    - `apply`: return the stashed files from the stash area back to where they were before the stash.
* `switch`: move to different branch or creats one if it doesn't exist yet.
- `restore`: to revert back to a previous version of a file from index or repository to working area.

* `log`: to see the history of the project (commits).
    * `--graph`: to see the history of the project in a graph format.
    * `--decorate`: to see the history of the project in a graph format with decoration.
    * `--oneline`: to see the history of the project in a oneline format (shorted).
    * `--patch`: to see the history of the project with details for every commit and what has changed in it.
    * `--grep <string>`: to filter the commits that has `string` in the commit message.
    * `-G <string>`: to see the commits that added or removed towards `string` files.
    * `-n`: to see the latest {n} commits.
    * `HEAD~5..HEAD^`: show me the .. to show range. it means show me show me the commits from 5 commits before HEAD to the parent of HEAD (`HEAD^`).

- `show`: to see the details of a commit (e.g. `git show 118c7b7`).
    - `HEAD@{time}`: to see the details of the head commit at a certain time. e.g. `git show HEAD@{1 month ago}`


* `blame`: to see the history of a file and what has changed in it along the timeline of the file itself.

- `rebase`:  taking the changes from one branch and applying them to another branch.
    - `-interactive`: to interactively rebase the changes.

* `reflog`: to see the history of commands that applied to the repository.

- `filter-repo`: to filter the repository by a certain pattern.

* `revert`: to revert the changes of a specific commit.
> **Warning**: be careful when you revert merges, because `revert` doesn't revert the structural merge of branches, only the changes that done to the content of them in new branch.


## 📦 CV Models:

<h4 align="center">There are multible models for version control systems</h4>

- <b>Peer to Peer model</b>: 
A peer to peer model is a model where two or more people are collaborating on a project without a public shared repo or any of them is controller and not centralized (purely distributed).

<br>

- <b>Centralized model</b>:
A centralized model is a model where one or more people are collaborating on the project with a shared online repository (server).

<br>

- <b>Pull Request model</b>:
A pull request model is a model where one or more people are collaborating on the project with a shared online repository (server) and the project is being updated by the people who are controling the project, other users can pull from it they doesnt push changes to the repository.

<br>

- <b>Dictator and Lieutenants model</b>:
A dictator and lieutenants model is a model for large projects, where the shared repo has access only from controler users, where they have a shared repo of their own that the end users of this model can change and push changes to them.

## 🌿 Branch Models

<h4 align="center">Naming is optional but Recommended</h4>

> **Note**: It's best to name branches based on their purpose.

- <b>Integration Branch</b>:
The integration branch is used to merge changes from other branches into the main branch. This allows changes to be tested and verified before they are merged into the main branch.

<br>

- <b>Release Branch</b>:
The Release branch is used to track changes that are ready to be released. This branch typically contains bug fixes and new features that have been tested and verified. 

<br>

- <b>Feature Branch</b>:
The Feature branch is used to track changes for new features. This branch typically contains code that is still being developed and tested.

<br>

- <b>Hotfix Branch</b>:
The Hotfix branch is used to track changes that need to be made to the code base urgently. This branch typically contains bug fixes that need to be released quickly.



> **Note**
> Course : Pluralsight - Mastering Git by Paolo Perrotta

