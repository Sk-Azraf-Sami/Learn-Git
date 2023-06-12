# Learn-Git
**If two contributors work on same project, how they create there own branch and merge it with main branch?**
<br>
When multiple contributors are working on the same project, they can follow the following steps to create their own branches and merge them with the main branch:<br>
 
1. Pull the latest changes: Before creating a new branch, it's important to ensure you have the latest changes from the main branch. Run `git pull` to fetch and merge the latest changes into your local repository.<br>

2. Create a new branch: Each contributor should create their own branch to work on their specific tasks or features. This helps in isolating their changes from the main branch and other contributors' work. To create a new branch, use the command `git branch branch-name`, where branch-name is the desired name for your branch.<br>

3. Switch to the new branch: After creating the branch, switch to it using the command `git checkout branch-name`. This will make the new branch the current active branch in your local repository<br>

4. Make changes and commit: Make the necessary changes to the project files in your branch. You can use git add to stage the changes and git commit to commit them with a descriptive commit message<br>

5. Push the branch: Once you have committed your changes, push the new branch to the remote repository using `git push origin branch-name`. This will make your branch available to other contributors.<br>

6. Review and merge changes: When you have completed your changes and are ready to merge them into the main branch, `create a pull request (PR)` on the hosting platform (e.g., GitHub, Bitbucket) from your branch to the main branch. The PR allows others to review your changes before merging them.<br>

7. Resolve conflicts (if any): If there are conflicts between your branch and the main branch, you'll need to resolve them. The hosting platform usually provides tools to help identify and resolve conflicts. Once conflicts are resolved, the changes can be merged.<br>

8. Merge the branch: After the changes have been reviewed and any conflicts are resolved, the branch can be merged into the main branch. This can typically be done through the hosting platform's interface or by using the command `git merge branch-name` while on the main branch.<br>

9. Repeat for other contributors: Other contributors can follow the same steps to create their own branches, make changes, create pull requests, and merge their changes into the main branch.<br>

By following this branching and merging workflow, multiple contributors can work on the same project simultaneously, collaborate effectively, and integrate their changes into the main branch in a controlled manner.<br>

**I need to switch main branch before "git branch branch-name" in 8th point.** <br>
Apologies for the confusion. In the 8th point, you should switch back to the main branch before creating a new branch.<br>
Here's the revised step: <br>
Switch to the main branch: Before merging the branch, switch back to the main branch using the command <br>
`git checkout main` (assuming the main branch is named "main"). This ensures that you are on the main branch when performing the merge.<br>
After switching to the main branch, you can proceed with merging the branch created by the contributor.<br>

**for mege operation, what will be my current branch?**
To perform a merge operation, your current branch should be the branch that you want to merge changes into. Let's assume you want to merge changes from a branch named "feature" into your current branch.<br>

If your current branch is already the branch where you want to merge the changes into (e.g., the main branch), then you don't need to switch branches. You can directly initiate the merge operation.<br>

However, if your current branch is not the branch where you want to merge the changes into, you need to switch to that branch first using the command `git checkout <branch-name>`. Replace <branch-name> with the name of the branch you want to merge changes into (e.g., git checkout main to switch to the main branch). <br>

Once you are on the desired branch, you can initiate the merge operation using the git merge command to merge changes from another branch into your current branch.<br>


<b>If I want to merge with main branch, I need to stay on main branch?</b> <br>
Yes, if you want to merge changes into the main branch, you need to make sure you are currently on the main branch.<br>

To switch to the main branch, you can use the following command:<br>
```
  git checkout main
 ```
Once you are on the main branch, you can initiate the merge operation to bring changes from another branch into the main branch using the git merge command. For example, if you have a branch named "feature" and you want to merge its changes into the main branch, you can use the following command:
```
git merge feature
```
This will merge the changes from the "feature" branch into the main branch.
