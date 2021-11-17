# New repository
* Create a repository
* Fork an existing project

# Add files to a repository
* On creation
* With the WebIDE
* From your client

# What happens on commit?

On your local machine you can make as many commits as you want, and nothing will happen.
But as soon as you push all of the automation we will configure will run.

* Trigger a CI/CD pipelines (you can skip with `ci skip`)
* Link issues and merge requests with keywords
* Start the collaboration and discussions
* When pushed you can cherry pick from UI
* Revert the commits
* Sign the commit with GPG

# Downloading contents

* Clone code via CLI
* Clone code via code editor
* Download all code in a compressed file (.zip, .tar, .tar.gz, .tar.bz2)
* Specific directories can be downloaded too
* Artifacts can be downloaded from the CI

# Analyzing Languages
At the bottom of the repository header you can see the language analysis.

https://docs.gitlab.com/ee/user/project/repository/img/repository_languages_v12_2.gif

You can change this behavior by overriding the default settings.

In your repository’s root directory, create a file named `.gitattributes`.
Add a line that tells GitLab to include files of this type. For example, to enable .proto files, add the following code:

`*.proto linguist-detectable=true`

Check support of markup languages https://docs.gitlab.com/ee/user/project/repository/#supported-markup-languages

# README

If you have a `README` or an `index` file, GitLab will automatically render its contents.
`README` takes priority over `index`.

Can contain these topics (depending on project)
* Information About the project
* Links to the Documentation
* Installation instructions
* Configuration instructions
* Operating instructions
* Contributing instructions
* Copyright and licensing information
* Troubleshooting instructions

# Graphs

## OpenAPI viewer
GitLab can render any OpenAPI specification files. The allowed keywords for filenames can be found here:
https://docs.gitlab.com/ee/user/project/repository/#openapi-viewer
To render an OpenAPI file:
* Go to the OpenAPI file in your repository.
* Between the Display source and Edit buttons, select Display OpenAPI. When an OpenAPI file is found, it replaces the Display rendered file button.

## Repository contributor graph
All code contributors are displayed under your project’s `Repository` > `Contributors`.
The graph shows the contributor with the most commits to the fewest.

## Repository history graph

A repository graph displays a visual history of the repository network, including branches and merges. This graph can help you visualize the Git flow strategy used in the repository.

Go to your project’s `Repository` > `Graph`.


# What happens when a repository path changes?

When a repository path changes, GitLab handles the transition from the old location to the new one with a redirect.
Same goes for renaming users, groups and repositories.
The redirects are available as long as the original path is not claimed by another group, user, or project.
