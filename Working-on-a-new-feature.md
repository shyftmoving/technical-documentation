You are a developer and a new ticket has been assigned to you? A common drill looks like this.  

1. Make sure that you have pulled the latest changes on `development` branch.
2. Create a branch with the following naming convention: `feature/SP-123`, where `SP-123` is the id of the Jira ticket assigned to you.
3. Once the branch is created, move the ticket from `TO DO` to `IN PROGRESS`.
4. Development is in progress
5. Do you have to commit something? Here are the [commit rules.](https://github.com/shyftmoving/technical-documentation/wiki/Commit-culture) we follow.
6. Do you need someone to have an early look at your code and have a discussion about it?
    - `YES` - Then [read about draft pull requests.](https://github.com/shyftmoving/technical-documentation/wiki/Draft-pull-requests)
    - `NO` - Cool.
7. Are you blocked by someone or something?
    - `YES` - Then [this is the document you are looking for.](https://github.com/shyftmoving/technical-documentation/wiki/Blocked-status)
    - `NO` - Even better, let's continue.
8. Do you think that the work on this ticket is done? Make sure to double-check the following:
    - Unit tests are written.
    - Integration tests are written.
    - All tests are passing locally.
    - Make sure that the implementation is tested manually.
9. Create a pull request from `feature/SP-123` to `development` branch.
10. Once the pull request is created, the build pipeline for the pull request will start. Once its completed, make sure that:
    - All tests are passing.
    - There are no code style warnings.
    - Static analysis of the code is completed successfully.

    If any of the points above are not passing, additional changes have to be made, so that the build pipeline on a pull request is passing successfully.
11. Once the pull request build pipeline passes without errors, move your ticket to `IN REVIEW` status.
12. Assign the person responsible for code review to the ticket. If the pull request requires multiple approvals, assign the project lead.
13. Pull request is merged? Continue reading [here]() then.

[![image alt text](https://github.com/shyftmoving/technical-documentation/wiki/assets/working-on-a-new-feature.png)](https://drive.google.com/file/d/1MADnq-D8APOZY77jbMprm0HmF2NMaFe5/view?usp=sharing)