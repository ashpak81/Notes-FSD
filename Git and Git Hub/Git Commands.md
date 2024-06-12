**Command to Push a File**  
1. `git init`  
2. `git add .`  
3. `git commit -m "Initial commit"`  
4. `git remote add origin <repository_link>`  
5. `git push -u origin master`  

`-m` stands for message  
`-u` stands for upstream  

**Command for Branches**  
- `git checkout -b "name_of_branch"`: This command creates a new branch and switches to it.  
- `git branch`: This command lists all branches available in the repository.  
- `git checkout "branch_name"`: This command switches to the specified branch.  
- `git merge "branch_name"`: This command merges the specified branch into the currently active branch.  
- `git branch -m old-branch-name new-branch-name`: Rename branch name.  
- `git clone <repository_link>`: Clone repository.  
- `git branch -d branch-name`: Delete the branch.
