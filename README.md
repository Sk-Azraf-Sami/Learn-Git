# Learn-Git

## Table of Contents

1. [Working with Branches and Merging](#working-with-branches-and-merging)
2. [Merging Branches: Staying on Main](#merging-branches-staying-on-main)
3. [Restoring All Branches After Cloning](#restoring-all-branches-after-cloning)
4. [Navigating to a Specific Commit](#navigating-to-a-specific-commit)
5. [Undo All Changes After Commit](#undo-all-changes-after-commit)
6. [Push Empty Directory to GitHub](#push-empty-directory-to-github)
7. [Confirming Which Files Are Ignored](#confirming-which-files-are-ignored)
8. [Top 5 Git Commands to Know](#top-5-git-commands-to-know)
9. [Removing .env File from Git Index Without Deleting Locally](#removing-env-file-from-git-index-without-deleting-locally)
10. [Connect GitHub Account with Git](#connect-github-account-with-git)
11. [Add Description with Commit](#add-description-with-commit)

## [Working with Branches and Merging](#working-with-branches-and-merging)
### If two contributors work on same project, how they create there own branch and merge it with main branch?
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

---

## [Restoring All Branches After Cloning](#restoring-all-branches-after-cloning)
### I deleted my repo from local but I upload it to github before deleting. Now when I clone, I get only main branch but I want to get back all branches in my local device.
<br>
If you have deleted the local copy of your Git repository but it still exists on GitHub, you can clone the repository again and fetch all the branches. By default, when you clone a repository, it only clones the default branch (usually "main" or "master"). To fetch all branches, you can follow these steps:

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/yourrepository.git
   ```

   Replace `yourusername` with your GitHub username and `yourrepository` with the name of your repository.

2. Change your working directory to the cloned repository:

   ```bash
   cd yourrepository
   ```

3. Fetch all remote branches:

   ```bash
   git fetch --all
   ```

   This command will fetch all branches from the remote repository on GitHub.

4. List all branches (both local and remote):

   ```bash
   git branch -a
   ```

   You should see a list of all branches, including remote branches from GitHub.

5. Create and switch to a local branch based on a remote branch:

   To work on a specific remote branch locally, you can create and switch to a new local branch based on that remote branch. For example, if you want to work on the "dev" branch:

   ```bash
   git checkout -b dev origin/dev
   ```

   This command creates a new local branch called "dev" and sets it up to track the "origin/dev" remote branch.

Now you have cloned the repository, fetched all branches, and can work on any branch you need.

---

## [Navigating to a Specific Commit](#navigating-to-a-specific-commit)

If you want to navigate to a specific commit in your Git history, you can use the `git checkout` command along with the commit hash or a branch name.

Here's how you can do it:

```bash
git checkout <commit_hash>
```

Replace `<commit_hash>` with the actual commit hash you want to go to. You can find the commit hash by using `git log` and copying the hash of the commit you're interested in.

For example:

```bash
git checkout abcdef123456
```

After running this command, your working directory will be in the state of the specified commit. Keep in mind that you will be in a "detached HEAD" state, which means you are not on a branch, and any changes you make won't be associated with a branch.
<br> 
Then use 
```bash
git checkout main
```

If you want to create a branch from this commit, you can do:

```bash
git checkout -b new_branch_name
```

Replace `new_branch_name` with the name you want for your new branch.

If you just want to view the files at a specific commit without modifying anything, you can use:

```bash
git show <commit_hash>
```

This will display the changes made in that specific commit.

Remember that going back in history in this way is a read-only operation. If you want to make changes or commits from this point, it's usually better to create a new branch.

---

## [Undo All Changes After Commit](#undo-all-changes-after-commit)
```bash
git restore .
```

---

## [Push Empty Directory to GitHub](#push-empty-directory-to-github)

Sure, here's a step-by-step guide on how to push empty folders to GitHub:

1. Open your terminal.

2. Navigate to the directory where you want to create the empty folder. For example, if you want to create an empty folder named `static`, you would use the command `cd path/to/your/project`.

3. Create the empty folder using the `mkdir` command. For example, `mkdir static`.

4. Git doesn't track empty folders by default. So, create a `.gitkeep` file in the `static` directory: `touch static/.gitkeep`.

5. Repeat steps 3 and 4 for any other directories you want to create. For example, for an `uploads` directory, you would use `mkdir uploads` and `touch uploads/.gitkeep`.

6. Now, add these changes to the staging area with `git add .`. The `.` tells Git to add all changes in the current directory and its subdirectories.

7. Commit these changes with `git commit -m "Add empty directories"`. This saves a snapshot of your changes.

8. Finally, push these changes to GitHub with `git push origin your-branch-name`. Replace `your-branch-name` with the name of the branch you're working on.

Now, when you go to your GitHub repository, you should see the `static` and `uploads` directories, even though they're empty.

Exmaple: 
```
# Ignore Python bytecode files
__pycache__/

# Ignore all files in static and uploads directories
static/*
uploads/*

# Except for the .gitkeep files
!static/.gitkeep
!uploads/.gitkeep
```

The `.gitignore` file you have is already set up to allow the `static` and `uploads` directories to be pushed to GitHub, even if they are empty. This is achieved by the `!static/.gitkeep` and `!uploads/.gitkeep` lines, which tell Git to not ignore these `.gitkeep` files.

However, Git doesn't track empty directories by default. The `.gitkeep` file is a convention used in the Git community to keep an otherwise empty directory under version control. The file could be named anything; `.gitkeep` is not a special name recognized by Git.

To ensure the `static` and `uploads` directories are pushed to GitHub, even if they're empty, you need to create a `.gitkeep` file in each of them:

```bash
touch static/.gitkeep
touch uploads/.gitkeep
```

Then, add and commit these `.gitkeep` files:

```bash
git add static/.gitkeep uploads/.gitkeep
git commit -m "Add .gitkeep files to static and uploads directories"
```

Now, when you push to GitHub, the `static` and `uploads` directories will be included, even if they're empty.

---

## [Confirming Which Files Are Ignored](#confirming-which-files-are-ignored)
To see which files are being ignored by Git based on your `.gitignore` file, you can use the `git check-ignore` command. Here's how you can do it:

```bash
git check-ignore -v <file_or_directory_path>
```

Replace `<file_or_directory_path>` with the path of the file or directory you want to check. This command will output the line in your `.gitignore` file that is causing the file or directory to be ignored.

For example, if you want to check if the `static` directory is being ignored:

```bash
git check-ignore -v static
```

If any specific file is being ignored, you can replace `static` with the file name you want to check.

**Another Way:**
If you want to confirm which files are ignored, you can run:

```bash
git status --ignored
```
This command will display a list of ignored files in your repository.


## [Top 5 Git Commands to Know](#top-5-git-commands-to-know)
### Top 5 git commands need to know - By Sahil, one of my favorite YouTubers:
Certainly! Here's an explanation of each of the Git commands you mentioned:

1. **Git Rebase**:
   - `git rebase` is used to reapply commits on top of another base tip.
   - It is often used to maintain a linear project history by moving, combining, or squashing commits.
   - When you rebase, Git takes the commits in your current working branch, "replays" them on top of the branch you're rebasing onto, and updates the branch pointer to the new commit.

2. **Git Fetch**:
   - `git fetch` is used to retrieve changes from a remote repository without merging them into the local branch.
   - It downloads the latest changes from a remote repository but doesn't apply them to your working branch. Instead, it updates the remote tracking branches (like `origin/master`), allowing you to see what others have been working on.

3. **Git Reset**:
   - `git reset` is used to move the HEAD and/or reset the index to a specific state.
   - It can be used to undo changes in your working directory and staging area (index).
   - There are three main modes of `git reset`: `--soft`, `--mixed` (default), and `--hard`, which determine whether changes are kept in the working directory, unstaged, or completely discarded.

4. **Git Cherry Pick**:
   - `git cherry-pick` is used to apply a specific commit from one branch onto another branch.
   - It's useful for selectively applying changes or fixes from one branch to another without merging the entire branch.
   - You specify the commit to cherry-pick by its SHA-1 hash or a reference (branch name, tag, etc.).

5. **Git Stash**:
   - `git stash` is used to temporarily store changes in your working directory and index, allowing you to switch branches or perform other operations without committing them.
   - It's useful when you want to work on a different task or address an urgent issue without committing incomplete changes.
   - You can later apply the stashed changes to your working directory using `git stash apply` or `git stash pop`.

These commands are powerful tools in Git that help manage and manipulate the history and state of your repository. It's important to use them carefully, especially when working with shared branches and repositories.

---

## [Removing .env File from Git Index Without Deleting Locally](#removing-env-file-from-git-index-without-deleting-locally)

The command `git rm --cached .env` is used to remove a file named `.env` from the Git index without deleting it from your local filesystem. This means that the file will no longer be tracked by Git, but it will remain on your local machine. 

Here's what each part of the command does:

- `git rm`: This is the Git command used to remove files from the Git index.
- `--cached`: This option tells Git to only remove the file from the index and not from the working directory. In other words, it unstages the file.
- `.env`: This is the name of the file you want to remove from the index. Replace `.env` with the name of the file you want to unstage if it's different.

After running this command, the `.env` file will no longer be tracked by Git, but it will remain in your working directory. Make sure to commit the changes to the repository after running this command to complete the process.

---

## [Connect GitHub Account with Git](#connect-github-account-with-git)

**Configuration** <br> 
Check connected user name
```bash
git config --global user.name 
```
Check connected email 
```
git config --global user.email
```

If any account is not connected, connect it 
```bash
git config --global user.name "github_user_name"
git config --global user.email "github_user_email"
```
But now every time need to give token as password. 

**Using SSH** <br> 
If you're having trouble connecting Git Bash to GitHub, it's likely that you haven't set up your SSH keys or configured your Git settings. Here are the steps to do so:

1. *Generate a new SSH key (if you haven't already)*
Open Git Bash and input the following command. Replace "your_email@example.com" with your GitHub email address.
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
When you're prompted to "Enter a file in which to save the key," press Enter to accept the default file location.
At the prompt, type a secure passphrase or leave it empty for no passphrase.

2. *Add your SSH key to the ssh-agent*
Start the ssh-agent in the background:
```bash
eval "$(ssh-agent -s)"
```
Add your SSH private key to the ssh-agent:
```bash
ssh-add ~/.ssh/id_ed25519
```

3. *Add your SSH key to your GitHub account*
Get the SSH key content:
```bash
cat ~/.ssh/id_ed25519.pub
```
Copy the output to your clipboard.
Go to GitHub, click on your profile photo, then click Settings. In the user settings sidebar, click SSH and GPG keys. Click New SSH key or Add SSH key. In the "Title" field, add a descriptive label for the new key. Paste your key into the "Key" field. Click Add SSH key.

4. *Confirm that you've connected to GitHub*
You can confirm that you've successfully connected your GitHub account to Git Bash by entering the following command:
```bash
ssh -T git@github.com
```
You should receive a message like this:
```bash
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```
This means that Git Bash is now successfully connected to GitHub.

---

## [Add Description with Commit](#add-description-with-commit)
You can add a description to your git commit by using the `-m` option twice. The first `-m` option will be the title of your commit and the second `-m` option will be the description. Here's an example:

```bash
git commit -m "Your commit title" -m "Your commit description"
```

The first `-m` is the short description (or title) of the commit and the second `-m` is the detailed description. The detailed description can span multiple lines if needed.
