- git

Git is a tool to control versions of code that each live independently on every system, this is in contrast to a centralized version system where each version is dependent on a main servers version of the code. Where a Centralized versioning system would update the main code on the server every time there is an edit, with git you can keep parts of your code that are only edited on your own machine, and send code to an agreed upon place without locking other versions out from editing. Typically Git is commanded from the command prompt, or power shell in Windows, and bash, or zsh in linux or Mac OS. Any commands listed here should be agnostic of whichever platform you use, though anything in "[ ]" brackets is a place holder, you would not have brackets there in a real command.  

- repository

If you view the code that you want to track with git as a shared folder, a repository is like a folder that holds each version of the code as a different folder. a new repository is started with the command `git init`


- remote

a Remote in git is the chosen repository that will be updated with any changes that you make on your own machine, when you choose to send those changes. To add a remote use the command `git remote add [name to call remote] [ssh or https address of remote]`

- branching

Branches are what git calls the different versions of code or likening back to folders, different folders inside of the repository. If you want to make some changes to the code and save them without breaking the working version of code, you would make a new branch, and when you work on this branch, you have to tell git that you are want it to update the branched version by checking it out. If you dont tell git you are working on a seperate branch it assumes you are editing the main version of code. the command to make a new branch named "beta" would be `git branch beta`.

- merging

when you want to take your edits in a branch and have them take effect in another branch, in git you preform a merge. this will try to replay the edits to the code or other files in a branch into the branch you have checked out though it doesnt directly use the version of the branch you are in, it uses a common ancestor of both to replay the edits until it finds something it cant justify, or it has reached the state of the changed branch.
To merge the beta branch to the Master branch the command would be `git merge beta` if run while the master branch was currently checked out.
- merge conflicts

merge conflicts are what git has when the merge 3 way comparison using a common ancestor where a branch left the source branch finds something it can not justify. This generally happens when both the source branch and the branch you are trying to merge with it have been changed. it will stop the merge and allow you to edit the conflicting files to the state you wish them to be in, and both versions will be in the file with special characters to denote which version they are from.
>An easy way to avoid this affecting the main branch of a repository is to keep the divergent branch up to date with the source branch where possible, so that if there is a conflict, it is in your divergent branch.

- the three git states:
  - modified

  files in a local folder that have been changed since the last tracked and submitted changes are considered modified.


  - staging

  files that were previously modified, and have been set to be tracked with the change will be considered in the staging area of git, this is also known as being indexed, such as what windows needs to do with files before you are able to search for them in the start menu. to tell git to stage a modified file you run the command `git add [filename]` or to stage all in the current directory `git add .` there are several other useful command options for specific cases to check out in git's documentation.

  - committed

  after staging any files that you want to be in your edits, and then running the command `git commit` or `git commit -m 'reason for changes'` with the only difference being whether git opens your text editor, since it requires a message with a commit, the changes will now be considered committed.
  What this represents is a point in time that git saves the state of all the files in your repository, and you can share this with others, or use it to request a merge with a repository online. later on you can restore files to one of these points as you develop a history of commits. Very useful indeed.
