1. `git init` -> Powers your folder to be managed by git, and initialises a new empty 
repository. It also creates a .git folder that has all the relevant logic to manage
versions of your project.


2. `Working Area` -> There can be a bunch of files that are not currently handled by git. 
It means that changes done or to be done in those files are not managed by git yet. A file 
which is in working area is considered to be not in the staging area. When we do `git status`
and we see abunch if `untracked files` then these are actually called to be in the working area.

3. `Staging area` -> What all files are going to be part of the next version that we will create.
This staging area is the place where git knows what changes will be done from the last version to
the next version.

4. `Repository Area` -> This area actually contains the details of all you previous registered version. 
And the files in this area, git already manages them and knows their version history. 


5. `git add <file>` -> moves file from working area to staging area

6. `git rm --cached <file>` -> moves file back from staging area to working area

7. `commit` -> Commit is a particular version of the project. It captures a snapshot of the project's staged
changes and creates a version out of it. 

8. `git commit` -> registers staging changes to a commit.

9. `git log` -> list downs all the commits of the repository. If you want to exit out of git log prompt
press `q`.

10. `git restore <file>` -> it removes all files changes from the staging area to be committed. This can
be useful, if we did some dirty piece of code and now no more want it. Instead of deleting every change 
line by line, we can restore it or you can say restore last clean version of the file. 

11. `git restore --staged <file>` -> it removes file from changes from staging area to the working area.
this only works if changes are in your staging area

12. Diff between git rm and git restore
ans: if you want to move the whole file back to the untracked state, then we do git rm, otherwise if we 
just want the changes to be moved in working area or staging area then we git restore.

13. `git diff commit1 commit2` -> gives the difference of all file changes between two commits

14 `git commit -m "<your commit message>"` -> If we want to avoid opening a text editor like vim/nano to 
add commit message we can use this following command

15. `git remote` -> list down all the remote connection names

16. Remote connection -> It helps you to link two git repositories for uploading and downloading changes
from each otherwise

17. `git remote add <name of remote> <link of the remote>` : this command helps us to add a new link to the
remote repo and give a name to it

18.  `git remote rm <name of remote>` : this command deletes a remote connection

19.  `git remote rename <olanme> <newname>` : this command remanes the remote connection

Note: The name of the remote connection is always used to establish communication between the repos

20. `git add <file1> <file2> <file3>`: this command will add multiple file changes together in the
staging area

21. `git add .`: this command will add all files from working repo to staging area.

22. `git pull <remote name> <branch name>` : downloads latest changes from the branch of the mentioned remote in your local repo.

### Recommended practice to do

    - make changes
    - git add <file>
    - git commit 
    - git pull
    - git push 
    
23. Merge conflicts are a very common scnario


merge conflicts can occur if multiple people try to make changes to the same file, and then collaborate 

----xxxxx----------xxxxxxxxxx
// some other commands

How to Create a Branch in Git :- 


1): Creating a Branch:- To create a branch, use the "git branch" command followed by the name of the branch. After making the branch, use "git branch" again to view available branches.
Notice that creating a branch this way does not automatically switch to the new branch. Git uses an asterisk and a different colored font to identify which branch is active. This designation represents the HEAD pointer showing which branch is active.

          git branch <branch name>  // command line to create a new branch 
          git branch  // using this command , you can easily see on which branch currently working 

2): Creating a Branch using Checkout :- If you want to create a branch and checkout the branch simultaneously, use the    "git checkout" command. The switch -b specifies the name of the branch. Note that after command completion, Git has moved HEAD to the new branch.

          git checkout -b <branch name> //is se directly main branch se ek new branch hogi aur usi branch pr move kr jaoge
          git branch // it is highly reccommend u to use this command contineously to see which bracn currently active 

3): Creating a Branch from Another Branch(not from main branch) :- Creating a branch from another branch is no different from creating from the main branch. You just need to specify the name of the other branch as the starting point. Note that after command completion, Git has moved HEAD to the new branch.

          git checkout -b feature4 develop // This example shows creating the feature4 branch from the develop branch

4): Download Branch from Remote Repository :- To retrieve the branch from the remote repository, use "git pull" against the origin and specify the name of the branch. If you check available local branches, the new branch doesn’t appear automatically. However, you can check out the branch and begin working on this new branch.
          
          git pull origin <branch name>
          git branch
	  git checkout <branch name>
	  git branch

Merging branch :-

1): Merging Branches in a Local Repository :- To merge branches locally, use git checkoutto switch to the branch you want to merge into. This branch is typically the main branch. Next, use git mergeand specify the name of the other branch to bring into this branch.

          git checkout main
	  git merge jeff/feature1 // This example merges the jeff/feature1 branch into the main branch.

2): Merging Branches to Remote Repository :- If you create a branch in your local repository, the remote repository is not aware of the branch’s existence. Before you can push the branch code in the remote repository, you set the remote repository as the upstream branch using the git pushcommand. This command simultaneously sets the upstream branch and pushes the branch contents to the remote repository.
	  
	  git push --set-upstream origin <branch name>


Deleting branches:- 

1): The -d option is an alias for --delete, which only deletes the branch if it has already been fully merged in its      upstream branch.

	   git branch -d <branch_name>

2): The -D option is an alias for --delete --force, which deletes the branch "irrespective of its merged status."

 	   git branch -D <branch_name> 

     


