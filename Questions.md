<ol>
      <li>Why do we ever need git?</li>
      <li>Centralized vs Distributed VC?</li>
      <li>what is a local repo?</li>
      <li>what is a remote repo? </li>
      <li>what is merge conflict? </li>
      <li>what is git commit —amend and force amend? </li>
      <li>what is merge? </li>
      <li>what is rebase? </li>
      <li>what is a working tree? </li>
      <li>what does git status do? </li>
      <li>What does git diff do? </li>
      <li>what is git pull? </li>
      <li>compare with git fetch? </li>
      <li>what is git push? </li>
      <li>what is git checkout? </li>
      <li>What is a branch? </li>
    <li>what is a tag? </li>
    <li>how to create a branch from git commands? </li>
    <li>What is git cherry-pick? What is pull-request/merge-request? </li>
    </ol>





1. Git is a distributed version control system that allows developers to track their code changes and revert back to specific versions if needed. 
2. Centralized version control systems (CVCSs) are typically used in software development. In a CVCS, there is a central server where all the code is stored and developers check out code from the server to make changes. Once they are done, they check the code back in and the changes are reflected on the server. 
3.  In a distributed version control system (DVCS), each developer has their own local copy of the codebase and can make changes without having to check out code from the server. Changes are only pushed to the server once the developer is ready to share their changes with others. 
4.  A local repository is a copy of a remote repository that is stored locally on your computer. A remote repository is a repository that is stored on a remote server. 
5.  A merge conflict occurs when two or more developers have made changes to the same line(s) of code in a file and those changes cannot be automatically merged. 
6.  Git commit --amend allows you to modify the most recent commit. Git commit --amend --force allows you to modify a commit even if it has already been pushed to a remote repository. 
7.  A merge is when two or more branches are combined. A rebase is when the commits from one branch are applied on top of another branch. 
8.  A working tree is the files that are checked out and available for you to work on. 
9.  Git status shows the status of the current working tree. Git diff shows the differences between the working tree and the index. 
10.  Git pull combines the changes from a remote repository with the local copy of the repository. Git fetch retrieves the changes from a remote repository but does not merge those changes with the local copy. 
11. Git push sends the changes from the local repository to a remote repository. 
12. Git checkout allows you to switch between different branches. 
13. A branch is a way to isolate development work from the rest of the codebase. A tag is a way to mark a specific commit. 
14. To create a branch from git commands, you can use the git branch command. 
15. Git cherry-pick allows you to apply the changes from a specific commit to another branch. 
16. A pull request is when a developer requests that the changes from their branch be merged into another branch. A merge request is when a developer requests that the changes from their branch be applied on top of another branch.