During the development by focusing too much on the implementation we lose the sense of the  the time. It happens that the commit and push operations do not happen for a longer (read: hours) period of time.

We should commit and push often during the day, as your colleague, team lead or someone else might want to take a peek into the current progress, not to mention the possibility of loosing the local data due to many hardware and software reasons. 

Even by doing the commits and pushes often during the day, we have to pay attention to the form in which these commits are defined. Therefore, let's have a couple of do's and don'ts in mind:

### Do

- Commit and push often
- Start your commit message with Jira ticket id, as Github will recognize and link the Jira ticket, which helps in navigating between the ticket and the commit.  
Example: `SP-123 Some description`.
- Limit commit subject to 72 characters.
- Define commit subject as concise and descriptive like: `SP-123 OpenID identity server integration`
- Use the imperative, present tense in commit messages.
```
Do: SP-123 Add Banji with animation
Don't: SP-123 Added Banji ... (past tense)
```
- If you think that the 10 commits you already made could look better in the commit history, feel free to squash these commits into a single commit with proper subject.
- Capitalize the subject line.
```
Do: SP-123 Fix title
Don't: SP-123 fix title (started with lower case)
```
- Define commit message with detailed description if necessary.  

    Console example:  
    `git commit -m "SP-123 Concise subject" -m "Detailed description"`

### Don't

- Avoid working on a feature and making a commit once you're done.
- Defining the uninformative subject like * `almost there`, `try2`,* etc  pollutes the commit history of the project and it is quite hard to go back to cherry-pick specific commit if necessary.
- Define the subject without knowing what has been worked on like `*Finished implementation*`
- Put the whole description into the subject.
- Commit without a push. If you specifically plan to separate changes into multiple commits and then to push the changes, that's fine. Otherwise, commit and push should go along all the time.

The ultimate goal is having commit logs like this:
```
$ git log --oneline -5 --author pwebb --before "Sat Aug 30 2014"

5ba3db6 Fix failing CompositePropertySourceTests
84564a0 Rework @PropertySource early parsing logic
e142fd1 Add tests for ImportSelector meta-data
887815f Update docbook dependency and generate epub
ac8326d Polish mockito usage
```

instead of:
```
$ git log --oneline -5 --author cbeams --before "Fri Mar 26 2009"

e5f4b49 Re-adding ConfigurationPostProcessorTests after its brief removal in r814. @Ignore-ing the testCglibClassesAreLoadedJustInTimeForEnhancement() method as it turns out this was one of the culprits in the recent build breakage. The classloader hacking causes subtle downstream effects, breaking unrelated tests. The test method is still useful, but should only be run on a manual basis to ensure CGLIB is not prematurely classloaded, and should not be run as part of the automated build.
2db0f12 fixed two build-breaking issues: + reverted ClassMetadataReadingVisitor to revision 794 + eliminated ConfigurationPostProcessorTests until further investigation determines why it causes downstream tests to fail (such as the seemingly unrelated ClassPathXmlApplicationContextTests)
147709f Tweaks to package-info.java files
22b25e0 Consolidated Util and MutableAnnotationUtils classes into existing AsmUtils
7f96f57 polishing
```