!SLIDE smbullets
# History of Git

* Linux kernel development
 * Patches and archives
 * Proprietary software `BitKeeper`
* Controversy in 2005, no more free to use
* Kernel developers invented `Git`

!SLIDE smbullets
# Design Goals for Git

* Speed
* Simple design
* Non-linear development (many branches)
* Fully distributed
* Handle large projects in speed and size


~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~


!SLIDE smbullets noprint
# Snapshots and Differences

* File changes and deltas over time
  * Git Commit, take snapshot, store reference to that snapshot
  * Set of snapshots of a mini-filesystem
  * No change - link to the previous identical stored file

<center><img src="../../_images/introduction/git_introduction_basics_01_changes.png" style="width:526px;height:305px;" alt="Basic Changes"/></center>

!SLIDE smbullets printonly
# Snapshots and Differences

* File changes and deltas over time
  * Git Commit, take snapshot, store reference to that snapshot
  * Set of snapshots of a mini-filesystem
  * No change - link to the previous identical stored file

<center><img src="../../_images/introduction/git_introduction_basics_01_changes.png" style="width:450px" alt="Basic Changes"/></center>


!SLIDE smbullets
# Work locally

* No network latency involved as with other VCS systems
* Local repository clone, fast operations
 * Browse the history
 * Show differences between specific branches
* Work offline and push changes later

!SLIDE smbullets
# Integrity

* Everything has a checksum (SHA-1)
* No changes possible without Git knowing about them
* Checksums are used everywhere
* Revert changes and even restore deleted files

Example:

    7f0b824ba55e1fd4ffc5c461df0a0f48a94195cc

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets
# The three states

* Working directory ("modified")
* Staging area ("staged")
* Git directory ("committed")

<center><img src="../../_images/introduction/git_introduction_basics_03_three_states.png" alt="Basics 3 States"/></center>


!SLIDE smbullets
# Basic Git Workflow

* Modify files in `working directory`
* Stage the files which add snapshots to the `staging area` ("git add")
* Commit ("git commit")
 * Takes files from `staging area`
 * Stores snapshot permanently in `.git directory`

~~~SECTION:handouts~~~

****

* If a particular version of a file is in the `.git directory`, it’s considered `committed`.

* `Staged` means that the file has been modified and it was added to the staging area

* `Modified` means that the file was changed since it was checked out but has not been staged yet.

~~~ENDSECTION~~~


!SLIDE smbullets
# Git CLI

* Work on the CLI
* GUIs implement partial feature sets of the CLI tool
* Shell sub commands
* Bash-completion


~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~


!SLIDE smbullets
# Git Command Overview

* Start a working area (clone, init)
* Work on current changes (add, reset)
* Examine the history and state (status, log)
* Grow, mark and tweak the history (branch, checkout, commit, merge, rebase)
* Collaborate (fetch, pull, push)

~~~SECTION:handouts~~~

****

Example from Git CLI command:

    start a working area (see also: git help tutorial)
       clone      Clone a repository into a new directory
       init       Create an empty Git repository or reinitialize an existing one

    work on the current change (see also: git help everyday)
       add        Add file contents to the index
       mv         Move or rename a file, a directory, or a symlink
       reset      Reset current HEAD to the specified state
       rm         Remove files from the working tree and from the index

    examine the history and state (see also: git help revisions)
       bisect     Use binary search to find the commit that introduced a bug
       grep       Print lines matching a pattern
       log        Show commit logs
       show       Show various types of objects
       status     Show the working tree status

    grow, mark and tweak your common history
       branch     List, create, or delete branches
       checkout   Switch branches or restore working tree files
       commit     Record changes to the repository
       diff       Show changes between commits, commit and working tree, etc
       merge      Join two or more development histories together
       rebase     Forward-port local commits to the updated upstream head
       tag        Create, list, delete or verify a tag object signed with GPG

    collaborate (see also: git help workflows)
       fetch      Download objects and refs from another repository
       pull       Fetch from and integrate with another repository or a local branch
       push       Update remote refs along with associated objects


~~~ENDSECTION~~~

!SLIDE smbullets
# Collaboration

* Work locally
* Push to remote repository
* Share your work with others
* Review, discuss, collaborate
* Change, adopt, release

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~