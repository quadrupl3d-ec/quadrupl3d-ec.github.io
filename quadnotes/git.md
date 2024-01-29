
1. Check the currently selected branch

        $ git branch
   
2. Create a different branch called `branch-name` and commit changes in that branch

        $ git checkout -b branch-name

3. Check your Git configuration, especially the remote URL
   
        $ git remote -v

4 Ensure that you have pushed the new branch to the remote repository (GitHub)

        $ git push origin branch-name

        // Sets the remote branch as upstream
        $ git push --set-upstream origin branch-name

5 Check the differences in the currently selected branch

        $ git diff

6 Add the current directory for tracking changes
        
        $ git add .

7 Global Configuration for git to make changes
 
        $ git config --global user.email "user@domain.in"
        
        $ git config --global user.name "user"

8 Commiting the changes.
           
        $ git commit -m 'commit message'

        $ git reset hard

9. Checking the log of all git commits

        $ git log

10. Ensure that the remote URL is using the correct SSH format. You can update it using the following command:

        $ git remote set-url origin git@github.com:username/forked-repo.git

11. Check if the SSH Tunnel is able to connect you to github.

        $ ssh -T git@github.com

12. Rebase the `new-feature` branch with the master branch.  
**How rebase works ?** <br>
Assume initially, the `new-feature` branch and the `master` branch are at the same level. Meanwhile the `new-feature` branch is still in development, `master` branch is getting upwards as some changes are pushed in this branch. Once the `new-feature` branch is developed, I want to push these changes on the top of master branch (which is now different from the old master branch)

        $ git rebase -i master

14. Pushes all the commits to the forked repo.

        $ git push -f

14 Delete a branch called `new-feature`

        $ git branch -D new-feature

15. The `git checkout --track origin/new-feature` command is used to create a new local branch based on a remote branch called `new-feature` and set up tracking between the local and remote branches.

        $ git checkout --track origin/new-feature

16 The `git pull --all` command is not a standard Git command. The git pull command is used to fetch and integrate changes from a remote repository into the current branch.

        $ git pull --all
