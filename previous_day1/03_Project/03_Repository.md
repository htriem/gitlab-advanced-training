!SLIDE smbullets
# Repository

* Web view of the Git repository
  * Files
  * Commits
  * Branches
* Possibility to edit/add files from your browser
* Remote Repository with clone details


~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets
# Lab ~~~SECTION:MAJOR~~~.~~~SECTION:MINOR~~~: Clone the Repository

* Objective:
 * Clone the repository into `$HOME/training`
* Steps:
 * Navigate into your `$HOME` directory
 * Extract the project URL (`Project > Details`)
 * Use `git clone https://.../devops/training.git training`
 * Inspect the files

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~

!SLIDE supplemental solutions
# Lab ~~~SECTION:MAJOR~~~.~~~SECTION:MINOR~~~: Proposed Solution
****

## Clone the Repository

****

Follow the instructions and ask the trainer for help in case.

    @@@ Sh
    $ cd $HOME
    $ git clone https://4014-gitlab-b1d71-web.nws.netways.de/devops/training.git training
    $ cd training
    $ git log
    $ ls -lah

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~
