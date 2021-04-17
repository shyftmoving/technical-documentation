# Branching strategy

## GitFlow

GitFlow is a process that has many shapes and understandings. A nice explanation is defined by Atlassian here, so I suggest going there and reading that stuff.

[Gitflow Workflow | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

Welcome back 🙂. Now, as with every process, it isn't black and white, as it has to fit into the overall process in every company. For the purposes of software production in Shyft, this is what we should pay the attention to.



## master/main

The branch we first see when the repository is created. This is the branch we won't push to too much, as we will reserve it for the purpose of production release. 

`master/main` branch is protected from direct commit/push.

That's why we define a development branch

## development

The `development` branch is de-facto the main branch for the development process on product. From the development branch, we will do the deployments to the `dev` and `qa` environment.

## feature branches

When the implementation on new task is started, a developer has to create a feature branch to work on it. Such branch is branched from the `development` branch, having the following recommendations in mind:

- make sure that the `development` branch is up-to-date with its remote counterpart
- naming convention: `feature/JIRA_TICKET_ID`.  
Example: `feature/SP-123` where `SP-123 is the ide of the ticket in Jira, a developer started to work on.
- do the implementation and sync often with the `development` branch.

## release branches

When the project manager decides to do the release, he/she will also decide what features to include in the release. At that moment, a `release` branch will be created out of the `development` branch. As the release branch is created, a pipeline for deployment to `staging` environment will kick in and deploy the content of the release branch to `staging` environment.

Naming convention for `release` branches isn't that strict as with `feature` branches. As long as it follows `release/*` pattern, where `*` can be replaced with short description, we're good.

## hotfix branches

Hotfix branches are used for production fixes and in its nature are identical to release branches. A `hotfix` branch is created out of `master/main` branch. Once the `hotfix` branch is created, or a commit to it has happened, a pipeline for deployment to `staging` environment will also kick in. 

As with `release` branches, hotfix branches should follow a similar naming convention: `hotfix/*`.