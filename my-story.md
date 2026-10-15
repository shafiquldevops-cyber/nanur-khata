Nanu’s Recipe Book — My Git Story

Introduction

This project is a collection of traditional family recipes inspired by Nanu’s cooking. I used Git and GitHub to manage the recipes, practice version control, and learn how to collaborate through branches and merges.

Recipes

* Bhapa Pitha
* Eid Special Biryani
* Chittagong Mezban
* Halua

Git Commands I Practiced

Command	Purpose
git init -b main	Initialize a Git repository with the main branch
git add	Stage files for a commit
git commit	Save changes in the repository history
git status	Check the working tree and staging area
git log --oneline	View commit history
git branch	List or manage branches
git switch	Switch between branches
git merge	Merge changes from another branch
git fetch	Download remote updates without merging them
git pull	Fetch and integrate remote changes
git push	Upload local commits to GitHub
git stash	Temporarily save uncommitted changes
git reset --hard	Reset the current branch and working tree to a chosen commit
git rm	Remove a tracked file and stage its deletion
git mv	Move or rename a tracked file

What I Learned

1. How to create a repository and track changes with Git.
2. How to create branches and merge recipe changes.
3. How to resolve a merge conflict by editing the conflicting file.
4. How to ignore secret and temporary files using .gitignore.
5. How to use git stash to save unfinished work temporarily.
6. How to clone a repository and synchronize changes between local repositories and GitHub.
7. How to use git reset --hard safely on a separate practice branch.
8. How to review commit history and check repository status.

Chapter 1: Understanding git diff and git diff –staged

I learned that git diff shows changes in tracked files that have not been staged yet. On the other hand, git diff --staged shows the changes that are already staged and ready to be committed.

For the bhapa pitha recipe, I practiced checking changes before committing them. I also used git reset bazar-list.txt to unstage the shopping list without deleting the file.

Chapter 3: Merge Conflict Resolution

I created a separate recipe-test branch and changed the gur quantity in bhapa-pitha.md. I also changed the same line on main, using a different quantity.

When I merged the branches, Git reported a merge conflict because both branches modified the same part of the file.

I opened the file, selected the version I wanted to keep, removed the conflict markers, and committed the resolved file. In my test branch, I kept two cups of gur, while the main branch retained its one-cup version.

Chapter 4: Fetch + Merge vs Pull

git fetch origin downloads new commits and updates remote-tracking branches, but it does not automatically merge those changes into my current branch.

After fetching, I used git merge origin/main to integrate the remote changes into my local branch.

git pull origin main combines fetching with integrating the remote changes into the current branch. It is a convenient way to update a local branch from a remote branch.

Chapter 5: Stash and Time Travel

I started an unfinished halua.md recipe and saved it temporarily with git stash. I then updated the biryani recipe to specify four green cardamom pods, committed the change, and restored the unfinished halua work using git stash pop.

I used git mv to move biryani.md into the recipes/ directory and git rm to remove shemai.md. I reviewed commit details with git show and file-change history with git log --stat -M.

What I Observed with git reset –hard

I created a separate reset-test branch from main and ran git reset --hard 8d9f43f.

The test branch moved back to the selected older commit. Later commits were no longer part of the reset-test branch history, but main remained unchanged. This demonstrated why it is safer to practise destructive Git commands on a separate branch.

Why Are Rebase and Reset –hard Dangerous on a Shared Branch?

Rebase rewrites commit history by creating new commits with different commit IDs. If other people are already working with the original commits, rewriting that history can cause confusion and integration problems.

git reset --hard moves the current branch to another commit and discards tracked working-tree changes. Commits that are no longer referenced by a branch may become difficult to recover. On a shared branch, this can disrupt other people’s work, especially if the rewritten history is pushed to the remote repository.

For these reasons, I practised git reset --hard on a separate test branch and kept my main branch unchanged.


Screenshots

The following screenshots are included as evidence of my Git practice and repository history.

1. Final Git History

This screenshot shows the final Git commit history and the branches used in the project.

2. Git History During Development

This screenshot shows the Git commit history captured during an earlier stage of the project.

Additional Evidence

Other screenshots, such as git diff, git diff --staged, .gitignore, merge conflict resolution, and stash operations, can be included if available.

Conclusion

This project helped me understand the basic Git workflow, branch management, conflict resolution, and remote repository synchronization through a practical recipe-book project.
