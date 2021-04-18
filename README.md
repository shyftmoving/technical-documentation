# Shyft technical documentation

This repository contains guidelines and explanations helpful to the member of the engineering department.  
Content of this repository is rendered in [Wiki pages](https://github.com/shyftmoving/technical-documentation/wiki)

## Cloning the documentation locally

Wiki pages are indenpendent git repository in the background. It means that technical-documentation repository and wiki pages are two different repository structures. This means that pushing to `main` branch of technical-documentation repository won't affect the content of wiki pages.  
Additionally, wiki pages repository isn't visible in Github UI, so it's imposible to have a pull request as we ordinarily have on other repositories on Github.  
Therefore, we've come up with a trick: Two remotes.

### Two remotes

To clone the technical documentation repo and wiki repo, follow these steps:
1. `git clone git@github.com:shyftmoving/technical-documentation.git`
2. `git remote add wiki git@github.com:shyftmoving/technical-documentation.wiki.git`
3. `git remotes -v`
  You should see something like this:
  ```
  origin	git@github.com:shyftmoving/technical-documentation.git (fetch)
  origin	git@github.com:shyftmoving/technical-documentation.git (push)
  wiki	git@github.com:shyftmoving/technical-documentation.wiki.git (fetch)
  wiki	git@github.com:shyftmoving/technical-documentation.wiki.git (push)
  ```
4. `git fetch`
5. `git fetch wiki`
6. `git checkout development`

#### Extras
7. `git checkout -b feature/ISSUE_ID`

As of this moment, you should be able to contribute to this project.


## How to contribute

The same rules apply to this repository as to every other in Shyft. To start, check out the [branching strategy](https://github.com/shyftmoving/technical-documentation/wiki/Branching-strategy).

1. Create an issue on this repo, describing what are you trying to accomplish.
2. Create a `feature/ISSUE_ID` branch and push your changes to it.
3. Create a pull request from your `feature` branch to `development` branch.
5. Once the pull request is approved, the following steps has to be taken, to deploy content to wiki:

### Deployment to wiki
1. Create a pull request from `development` to `main`.
2. Double check if everything is ok by self-reviewing the pull request.
3. Merge the pull request.
4. `git fetch`
5. `git checkout main` (where `main` is branch on `technical-documentation`repository)
6. `git pull`
7. `git checkout master` (where `master` is branch on `technical-documentation.wiki`repository)
8. `git merge main` (merging content from repo to wiki.repo)
9. `git push`

By pushing content to `master` branch of wiki repo, Github automatically renders the Wiki pages and the content should be live instantly.
