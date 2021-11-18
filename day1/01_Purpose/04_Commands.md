!SLIDE smbullets
# Start a project

* `git clone`
  * Clone a copy of existing remote repository.
  * Can be newly created in GitLab/GitHub and empty.
* `git init`
  * Initialize a local empty Git repository.

~~~SECTION:handouts~~~

****

`git clone` clones a copy of an existing remote Git repository.

`git init` initializes an empty directory as local Git repository.

When you clone a repository, Git automatically adds a shortcut called
`origin` that points back to the "parent" repository, under the assumption
that you'll want to interact with it further on down the road. This is
called an `origin`.

~~~ENDSECTION~~~

!SLIDE smbullets
# Add current changes

* `git add`
  * Add new files to Git (staged)
  * Add modified file(s) from the working directory into the staging index.
  * `-A` adds all files. Question: Where is this applicable?
* `git mv`
  * Rename file(s) tracked by Git.

~~~SECTION:handouts~~~

****

`git add` will add the file(s) and their content to the staging index
waiting for the commit. This applies to both, new files and also modified
files.

If you're using `-A` to add all files, you need to ensure that
unwanted files are not added. Learn more about `git reset` in the next
slide to selectively unstage added changes.

`git mv` renames an existing file tracking the change for the commit. If you
manually move the file, you will need to rm and add it again.

~~~ENDSECTION~~~

!SLIDE smbullets
# Remove changes

* `git reset`
  * Reset files added to the staging index.
  * Hint: This comes in handy with `git add -A` before.
* `git rm`
  * Remove the file(s) from working tree and Git repository.
  * Note that file(s) will be visible in Git history, and can be restored from it.
* `git rm --cached`
  * Alternative suggested by Git CLI for `git reset`

~~~SECTION:handouts~~~

****

`git reset` resets files added to the staging index. You can also use it to
reset commits from the history.

This also is helpful when you need to add 95 out of 100 changes. First, use `git add -A`
and then selectively unstage the unwanted 5 changes.

`git rm` removes the file from the working tree and also from the git index.

~~~ENDSECTION~~~

!SLIDE smbullets
# Examine the current state

* `git status`
  * Show current working tree status.
  * Modified files
  * Modified and added to staging for commit
  * Untracked files

Later we will learn how to compare specific commits and branches too.

~~~SECTION:handouts~~~

****

`git status` shows the current working tree status. Untracked files and changes (not) staged
for commit.

~~~ENDSECTION~~~


!SLIDE smbullets
# Examine the current state: Diff

* `git diff`
  * Compare changes between modified working tree and latest commit.
  * Output is a unified diff similar to `diff -ur file1 file2`.

Later we will learn how to compare specific commits and branches too.

~~~SECTION:handouts~~~

****

`git diff` shows changes between the current working tree and the last commit. You can
also compare specific commits.

~~~ENDSECTION~~~

!SLIDE smbullets
# Exclude files with .gitignore

* Build directories from source code compilation (e.g. `debug`, `release`)
* Files generated at runtime (e.g. test results or stats)
* User specific IDE settings
* Local Vagrant boxes and other temporary files

~~~SECTION:handouts~~~

****

You can use wildcard pattern matches for files.
If you'll end the string with a '/' git will only
ignore directories instead of both directories and files
matching the pattern.

If you want to ignore a file globally in your repository
you can preceed the path with `**/` which means `any directory`.

Example for ignoring a debug file anywhere in your repository:

    **/debug

If you prefer to keep `.gitignore` files in specific directories
and not a global file, this will also work.

~~~ENDSECTION~~~


!SLIDE smbullets
# Git Commits

* View as history log on production changes
* Keep the subject short, simple and explaining
* Make it easier for others understanding the changes
* Add detailed explanations on larger changes
* Add references to existing commits and/or ticket ids for further details

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets
# Work on Git History

* `git commit`
 * Selected changes from the staging index
 * All changes (`-a`) not necessarily added to the staging index
* Verbose mode shows changes compared to latest commit (`-v`)
* Uses the configured editor (vim, nano, etc.)
 * `-m` allows for a short commit message without editor view

Commits use the `user.name` and `user.email` settings to qualify
you as the author of this change. In addition to that the date
and time is stored.

~~~SECTION:handouts~~~

****

`git commit` collects and records all changes stages for commit. It uses the configured
user name and email address as commit author. This command opens the configured editor
requiring you to add a commit message.

~~~ENDSECTION~~~

!SLIDE smbullets
# Good Commits

* Selectively add changes for commit (do not commit everything)
 * `git add` for all changes in a file
 * `git add -p` for interactive selection of changes in a file
* `git commit <file1> <file2>`
* Enable the verbose mode `-v` to show the differences below the editor
 * Write a short summary based on the visible changes

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets
# Commit Message Overview

* Pick a short telling subject (max. 80-120 characters)
* Add a new line
* Add a body text explaining the issue (max. 80-120 characters in a line)
* Optional: Add external reference markers, e.g. for ticket systems

Example:

    A short subject for the commit line
    <newline>
    Some body text explaining the issue.
    80-120 characters max width.
    <newline>
    refs #<ticketid>

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets
# Examine the Git history

* `git log`
  * Show commit history of the current branch.
  * Supports `-10` notation to show a limited number of commits.

* `git blame <filename>`
  * Show authors of a certain file line-by-line
  * Supports `--color-lines` notation for grouping lines of the same commit.

~~~SECTION:handouts~~~

****

`git log` shows the commit history of the current branch.
`git blame <filename>`shows the author line-by-line of the selected file.


~~~ENDSECTION~~~

!SLIDE smbullets
# Examine the Git history

* `git show`
  * Print commit details.
  * If the commit id is omitted, the last commit is printed.
  * Supports `-10` notation to show a limited number of commits.
* `git diff`
  * Show changes between working tree and last commit.
  * Supports source and target parameters.
  * Can be used to compare 2 commit ids, branches, etc.

~~~SECTION:handouts~~~

****

`git show` will print the last commit details. If you want to print a specific commit id, add
it afterwards.

`git diff` shows changes between the current working tree and the last commit. You can
also compare specific commits.

~~~ENDSECTION~~~

!SLIDE smbullets
# Amend changes to commits

* Change the commit message, e.g. typos or missing changes broke the build
* Amend changes from staging
* Helps if new files were added but not committed
* `git commit --amend` changes the latest commit
 * Amending commits in Git history is possible, explained later with `git rebase`.

If you amend changes to a specific commit, a new unique commit id is generated.
This changes the Git history and we will learn later how to resolve possible
problems in collaboration with others.

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~


!SLIDE smbullets
# Working with Git branches

A git branch creates a new history line starting from the current
git commit.

Branches are useful to develop features/fixes in their isolated
environment.

* Master branch
* Develop a new feature in a dedicated branch
* Put fixes into the master branch (production)
* Continue to work on the feature

!SLIDE smbullets
# Git Branch CLI commands

* `git branch`
 * Create new branch without leaving the current one.
 * Delete branches
 * List branches
* `git checkout`
  * Switch between branches

~~~SECTION:handouts~~~

****

`git branch` allows you to list, create and delete branches.

`git checkout` will switch between branches.

~~~ENDSECTION~~~

!SLIDE smbullets
# HEAD and "smart pointers"

A git commit is unique and identified by its SHA1 checksum.

`HEAD` is a pointer to the latest commit in the current branch.

`HEAD^` identifies the second latest commit.

`HEAD~9` points to the tenth latest commit. Counting starts at zero.

This can be used for `git show`. More advanced techniques will be discussed later.

~~~SECTION:handouts~~~

~~~ENDSECTION~~~

!SLIDE smbullets
# Reset Git Commits

* `git reset`
  * Remove the current commit(s).
  * `--soft` adds changes to the staging index.
  * `--hard` drops them.
* Requires a new commit base specified with `HEAD` or any other pointer.
  * `HEAD~3` points to the 4th commit back in the history, resetting the latest 3 commits

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~

!SLIDE smbullets
# Collaboration: Put History

* `git push`
  * Update remote references and push local history to remote repository.
  * This pushes source code changes and commits.
  * Halts if the remote history diverged from your local history.
* `git remote`
  * Configure/list remote repository URLs (default `origin`).
* `git branch -r`
  * List remote branches, prefixed with the remote name, e.g. `origin/master`.

~~~SECTION:handouts~~~

****


`git push` updates remote references and pushes your local commit history to the remote repository.

`git remote` allows you to configure and list the remote repository. By default this is called `origin`.

~~~ENDSECTION~~~


!SLIDE smbullets
# Collaboration: Branch Tracking

* Local branches track remote branches
* Use same names for local and remote branches
 * Enables "simple" push with `git push` in the current checked out branch
* `git branch -a` lists all branches
* Use `git branch -vv` to list tracking

<center><img src="../../_images/collaboration/git_branch_tracking.png" alt="Tracking"/></center>

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~


!SLIDE smbullets
# Collaboration: Get History

* `git fetch`
  * Update the remote branch reference pointers to the latest commit and cache it locally.
  * Does not pull in any remote commit history.
* `git pull`
  * Fetch and update the local history from remote repository (implicit fetch).
  * This pulls in source code changes and commits.

~~~SECTION:handouts~~~

****

`git fetch` downloads objects and references from another remote repository.

`git pull` invokes a fetch and updates the local history with commits from the remote repository.


~~~ENDSECTION~~~

!SLIDE smbullets
# Git Tags

* Tag specific points in history
* Add, list, delete
* Push tags to remote repository
* Checkout branches based on tags
* Release software versions based on tags (e.g. v2.9.0)
* Tags can/should follow milestone versions in ticket systems

~~~SECTION:handouts~~~

****

Example for checking out a tag into a new branch:

    @@@ Sh
    $ git checkout -b version01 v0.1
    $ git branch

~~~ENDSECTION~~~

!SLIDE smbullets
# Advanced Git Commands: Stash

* `git stash`
 * Put current changes on a temporary stack.
 * Useful when changing branches (diff would not apply)
 * Use with care, pop changes immediately after changing back
 * Only local, not stored in the central repository

Example:

    @@@ Sh
    $ git stash
    Saved working directory and index state WIP on master: 4b4f6c2 <msg>

    $ git stash pop
    Dropped refs/stash@{0} (43d879b99aca12b6175c5362339b177af22589a9)

~~~SECTION:handouts~~~

****

`git stash` allows you put your current changes on a temporary stack (`stash`).
This comes in handy when you want to change branches with a different history
where your uncommitted changes will not apply.
Use `git stash pop` to fetch the changes again. You can stash multiple uncommitted
stages, `git stash list` will list them.

~~~ENDSECTION~~~

!SLIDE smbullets
# Advanced Git Commands: Cherry-Pick

* `git cherry-pick`
  * Collect specific commit into your working tree.
  * Applies the contained patch
  * When the base commit differs, checksum changes = new commit id
  * Use `git cherry-pick -x <sha1>` to add source comment

~~~SECTION:handouts~~~

****

`git cherry-pick` collects a specific commit into your working tree.


~~~ENDSECTION~~~