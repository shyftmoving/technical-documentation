Every moment is a perfect moment for code review. A review of the code your colleague in the team wrote, gives you a perfect opportunity to check its excellence and learn something new.  
Regardless of the experience each one of us has, almost every code review brings something new, and I think it's beautiful.  

Now you might want to ask yourself, what this guy is talking about?  
Fair enough, let me explain.

## How can I review someone's code
When a team member creates a pull request, there is an opportunity to review its code by opening the pull request and exploring the changes of the files.  
You might be assigned as a direct reviewer or not, but regardless of the assignment, nothing stops you to explore someone's implementation through code review and leave a comment or two.

## What is the purpose of the code review
The majority of the dev community thinks of code review as an instrument of control over the code. Sadly, that turns out to be true if only one person, always, reviews every pull request. Usually, such a person is a system architect, team lead, or office director.

I think that the code review serves the purpose of discussing and sharing the knowledge, experience and different approaches between team members. The code in the subject is just a topic that defines the discussion initially.

## What is the outcome of the pull request
- We learned something new today.  
- We helped someone.  

And as a side-effect we will have:  
- Better code.  
- Cleaner code.  
- Optimized code.  
- Code with less bugs.

## How do we do a code review?
As code review is important, and very useful, it is also very fragile. Therefore, we have to approach it carefully.  

Our colleagues in the team, as we are as well, are often personally attached to the code they wrote. That turns out to be the biggest obstacle in the code review process as drawing attention to the flaws in the implementation can be understood as an attack to them personally and their knowledge.  
If that's the case, the discussion won't be objective and there is no guarantee that we will get a useful outcome out of the review process.  

To avoid such a situation, let's try to follow a couple of simple steps:
1. If you are a reviewer, start your review with the positive attitude in mind.
    - You are not searching for flaws only.
    - You are looking for awesome stuff to praise, because it is awesome and you know it. Then say it.
        - _Wow, I didn't knew this is possible, good job! Do you have any links for me to read in details? Thanks!_
2. If the code you wrote is being reviewed, be aware that the review process is not about you, or your knowledge, but about the code we're pushing into our product. 
3. If the code you wrote is being reviewed, approach to it as a third person. You will be happy if you and your colleague figure out a newly introduced bug, because that's one less bug being discovered by QA, or user in the worst case.
4. Don't start an argument. If there are four or more replies on a single comment, that's a pretty good sign that you're on a slippery slope and wasting time on a conversation. You need a third opinion and get over it.
5. Avoid negative criticism. Come up with a suggestion instead and encourage a colleague to think of solution
    - _~~"If user leaves empty field this will break. We need a validation and test."~~_
    - _I'd suggest thinking of use case when user leaves an empty field. Maybe we need an additional test to cover it?_
6. Being a reviewer, doesn't give a special powers. Pay attention to common do's and don'ts when leaving a comment in the code review:

    ### Do
    - You found something awesome? Then say it!
        - _Wow, I didn't knew this is possible, good job! Do you have any links for me to read in details? Thanks!_
    - Its ok to nitpick, however make it obvious to everyone by putting `nit`.
        - _nit: Can we remove this newline please. Maybe its my OCD, and maybe we need a new rule for StyleCop?. :)_
        - _nit: I think brackets will increase the readability here?_
    - Be friendly when things aren't looking good. Make it obvious that you found a major flaw, but you have a trust it'll be fixed.
        - _Hey you probably skipped authorization on this admin endpoint._
        - _Hm, it looks like we're missing a database transaction here. It will most probably work in 99% of cases, but we want to make sure of atomic operation in this case._
        - _Usually ternarry operator helps in shortening the lines count, however I think that the complexity of this statement should be broken down into simple `if-else` to increase the readability a bit._
    ### Don't
    - We are not in a position to order something to anyone.
        - _"Fix this"_ or a polite version _"Fix this, please."_ isn't useful.
        - "_Replace this_"  
        This is usually a recipe for a disaster as you might get a really short answer: _"I disagree"._ After this its really hard to move on with a friendly and constructuve conversation.
    - Comments without actual value.
        - _OMG what is this?_
        - ???
    - Passive aggresive and toxic comments
        - Pasting a link to documentation without an additional explanation.
        - Pasting a link to documentation for beginners.
        - _In the documentation this is specifically noted not to do._
        - _Are you fu**ing serious!? People are getting fired for stuff like this!_