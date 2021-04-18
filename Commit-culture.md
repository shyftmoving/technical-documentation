During the development by focusing too much on the implementation we lose the sense of the  the time. It happens that the commit and push operations do not happen for a longer (read: hours) period of time.

We should commit and push often during the day, as your colleague, team lead or someone else might want to take a peek into the current progress, not to mention the possibility of loosing the local data due to many hardware and software reasons. 

Even by doing the commits and pushes often during the day, we have to pay attention to the form in which these commits are defined. Therefore, let's have a couple of do's and don'ts in mind:

### Do

- Commit and push often
- Start your commit message with Jira ticket id, as Github will recognize and link the Jira ticket, which helps in navigating between the ticket and the commit.  
Example: `SP-123 Some description`.
- Limit commit subject to 72 characters.
- Define commit subject as concise and descriptive like: `SP-123 OpenID identity server integration`
- If you think that the 10 commits you already made could look better in the commit history, feel free to squash these commits into a single commit with proper subject.
- Define commit message with detailed description if necessary.  

    Console example:  
    `git commit -m "SP-123 Concise subject" -m "Detailed description"`

### Don't

- Avoid working on a feature and making a commit once you're done
- Define the subject like *`fix`, `almost there`, `try2`,* etc as this pollutes the commit history of the project and it is quite hard to go back to cherry-pick specific commit if necessary.
- Define the subject without knowing what has been worked on like `*Finished implementation*`
- Put the whole description into the subject. 
- Commit without a push. If you specifically plan to separate changes into multiple commits and then to push the changes, that's fine. Otherwise, commit and push should go along all the time.