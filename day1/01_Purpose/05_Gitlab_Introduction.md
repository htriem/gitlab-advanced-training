!SLIDE smbullets
# Introduction

* Central storage for repositories
* Collaboration between teams
* User based access control
* Trigger events (e.g. for CI)

~~~SECTION:handouts~~~

****

There is a variety of Git server tools, web interfaces
and addons out there.

* GitLab
* gitosis
* gitolite

In case you don't want to host your own Git server,
there are open source and enterprise hosting options available.

NETWAYS also provides GitLab hosting services:

* https://www.netways.de/managed_hosting/gitlab_ce_hosting/
* https://nws.netways.de/products/gitlab-ce

~~~ENDSECTION~~~
!SLIDE smbullets
# Git Server Overview

* Git server daemon
* Web interfaces
* Entire collaboration suites
  * GitHub
  * GitLab
  * Bitbucket


~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE smbullets noprint
# GitLab

<center><img src="../../_images/server/git_server_gitlab.png" style="width: 800px;" alt="GitLab"/></center>

!SLIDE smbullets printonly
# GitLab

<center><img src="../../_images/server/git_server_gitlab.png" style="width:450px" alt="GitLab"/></center>
!SLIDE smbullets noprint
# GitHub

<center><img src="../../_images/server/git_server_github.png" style="width: 800px;" alt="GitHub"/></center>

!SLIDE smbullets printonly
# GitHub

<center><img src="../../_images/server/git_server_github.png" style="width:450px" alt="GitHub"/></center>


!SLIDE smbullets
# Git Server Protocol

* Read/write access via SSH
  * `git@github.com:username/repo.git`
* HTTPS protocol (write access via oauth tokens)
  * `https://my-gitlab.nws.netways.de/username/repo.git`
* Git protocol
  * `git://domain.com/repo.git`
* Local protocol
  * `file:///opt/git/repo.git`

!SLIDE smbullets
# GitLab Introduction

GitLab is available as self-hosted or cloud based repository management
system.

* Git repositories
* User and group management and fine granular permissions
* Issue tracking and project management (dashboards, etc.)
* Merge, review, report
* Continuous integration/deployment (CI/CD)

Hosted: https://www.netways.de/managed_hosting/gitlab_ce_hosting/

NWS: https://nws.netways.de/products/gitlab-ce

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~

!SLIDE smbullets
# GitLab Editions

* Community Edition (CE), Open Source and free to use
* Enterprise Edition (EE), additional features
  * Multiple LDAP servers, LDAP group import
  * Search backend with Elasticsearch, additional HA capabilities
  * Dependency Scanning, Audit logs
  * Merge Request Review Approvals, Issue Relations
  * Burndown charts
  * Epics, manage group of issues over many projects

https://about.gitlab.com/pricing/self-managed/feature-comparison/
https://about.gitlab.com/install/ce-or-ee/

~~~SECTION:handouts~~~

****

Overview: https://about.gitlab.com/features/
Comparison: https://about.gitlab.com/images/feature_page/gitlab-features.pdf

The source code is publicly available for both editions.
You'll need a valid license for running EE in production.

~~~ENDSECTION~~~


!SLIDE smbullets
# GitLab Components

* Ruby on Rails application (unicorn, sidekiq)
* Nginx webserver
* PostgreSQL database backend
* Redis cache
* NodeJS for Javascript rendering
* Golang for background daemons

It is recommended to use the Omnibus installation package or use
a managed cloud hosting service.

~~~SECTION:handouts~~~

****


Omnibus packages: https://about.gitlab.com/installation/?version=ce

More details on the manual installation instructions can be
found in the official documentation: https://docs.gitlab.com/ce/install/installation.html

~~~ENDSECTION~~~

!SLIDE smbullets
# Git Server Installation

This training focuses on a pre-installed GitLab instance.

Each user gets access to NWS - https://nws.netways.de
and a GitLab CE app.

GitLab supports working with

* SSH
* HTTPS

Manual installation instructions are provided in the
handout.

~~~SECTION:handouts~~~

****

~~~ENDSECTION~~~


!SLIDE smbullets
# Lab ~~~SECTION:MAJOR~~~.~~~SECTION:MINOR~~~: Create GitLab app in NWS

**Note**: Skip this lab if already done.

* Objective:
 * Create a new GitLab app in NWS
* Steps:
  * Navigate to https://nws.netways.de and register a trial account if not existing
  * Choose Apps > GitLab CE > Basic
  * Deploy the app
  * Choose Access and Live View and set a secure password for the `root` user.
  * Login

~~~SECTION:handouts~~~

****


~~~ENDSECTION~~~

!SLIDE supplemental exercises
# Lab ~~~SECTION:MAJOR~~~.~~~SECTION:MINOR~~~: Create GitLab Project

## Objective: Create a new GitLab app in NWS
****

* Create a new GitLab app in NWS

## Steps:

****

* Navigate to https://nws.netways.de and register a trial account if not existing
* Choose Apps > GitLab CE > Basic
* Deploy the app
* Choose Access and Live View and set a secure password for the `root` user.
* Login


!SLIDE supplemental solutions
# Lab ~~~SECTION:MAJOR~~~.~~~SECTION:MINOR~~~: Proposed Solution
****

## Create a new GitLab app in NWS

****

Open https://nws.netways.de in your browser and register your
personal account. Login and navigate to Apps > GitLab CE > Basic
and deploy the app.

Use Access and Live View and set a secure root password.
Then login into GitLab.


