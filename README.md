# GitLab Advanced Training

This [training](https://www.netways.de/trainings/gitlab/) is designed
as a one days hands-on training introducing GitLab, Workflows, CI/CD and
many best practices with GitLab.

The [GitLab Training](https://github.com/NETWAYS/gitlab-training) with
learning Git is recommended before taking this course.

The CI exercises follow with a real programming example in Golang, with later creating packages from them. The training aims to be more of a workshop with less explanations. 

## Overview

- GitLab Introduction: Purpose, Community/Enterprise Edition, Features 
- GitLab Basics: Users, Groups, Projects, Authorization (LDAP/AD), Administration, Dashboards
- Working with GitLab: Repositories, Web IDE, Branches, Issue Management (Templates, Labels), Release Management (Milestones), Best Practices
- GitLab Workflow: Merge Requests, Reviews + CI 
- Insights into GitLab: Project Graph, Kanban Issue Boards, Snippets, Wiki, etc. 
- CI/CD: Overview, Runners (Linux/Unix, Windows, macOS), Containers/Docker, Configuration (Variables, Templates), Pipelines (Jobs, Stages), Artifacts/Caches
- Advanced CI/CD: Container Registry, Custom Image Build, Package Jobs, Coverage Reports, Tests, Badges, Async Pipelines

## Official Training

We have developed our training material based on years of experience in
development, professional services and training. To support our work,
please join the official training sessions and get your ticket at [NETWAYS](https://www.netways.de/trainings/gitlab/).

## Provide your training

Requirements:

* Docker
* https://nws.netways.de GitLab instances for the trainer and participants

Start the presentation with the default settings:

```
./global/wizard.sh
[Enter]
[Enter]
```

More instructions [here](https://github.com/NETWAYS/training-global#using-docker-to-build-and-serve-the-slide-deck).

### Environment

The training material focuses on https://nws.netways.de where every attendee
gets their own GitLab instance.

The [vm/](vm/) directory provides a fallback VM which can be exported
from Vagrant/VirtualBox and is provisioned onto the training notebook @NETWAYS.

### Trainer

Additional trainer introduction slides can be [provided](https://github.com/NETWAYS/training-global#2-create-a-directory-to-provide-trainer-introduction).

# Contribution

Patches to fix mistakes or add optional content are always appreciated. If you want to see
changes on the default content of the training we are open for suggestions but keep in mind
that the training is intended for a two day hands-on training.

The rendered content will be updated at least if we do a newer version of the material which
will also be tagged on git.

Material is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-nc-sa/4.0/).


