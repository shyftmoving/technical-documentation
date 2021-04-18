Pull request is nothing but the request for someone else in the team to merge the changes from one branch into another.  
`dev` and `master/main` branches are protected from direct pushes. Therefore, every change on these branches has to happen through the pull request.

### When do we create a pull request?

- If we want to consult with other colleagues, we can create a [draft pull requests.](Draft-pull-requests) on Github to discuss the implementation prior official pull request.
- when we are done with implementation, we create a pull request from our `feature/SP-123` into the `development`
- when we are done with the bugfix, we create a pull request from our `hotfix/minor-issue` into the `master/main`
- when we are about to release a new version into production, we create a pull request from our `release/feature-001` branch into the `master/main`.
- when we need to sync changes in our `hotfix` or `release` branches with `development`, we have to create a pull request from these branches into the `development`.

### Who should review the pull request?

- As a rule of thumb, tech lead for specific platform should be included as a reviewer of every pull request.
- Number of approvals should guarantee that the code quality is satisfactory. Required number of approvals depends of team size on specific platform. For example:  
    - Team size: [1-3]: 1 approval required. 
    - Team size per platform: [4-9): 2 approvals required.
    - Team size per platform >10: 3 approvals required.

### Merging the pull request
Once we agree that the quality of implementation is satisfactory, then we move on with the merge operation. During the pull request merge, we should do the following:
- Make sure that the pull request title is descriptive enough, as it will remain in the commit history;
- Check the option to squash all commits.
- Delete the source branch having in mind the following rules:
    - If its a `feature` branch, we will delete it.
    - If its a `release` or `hotfix` branch, and we're merging into `master/main`, we will delete it.
    - If its a `release` or `hotfix` branch, and we're merging into `dev`, we will NOT delete it.
