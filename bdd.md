# BDD

## Introduction

Behavior Driven Development is a process where we define the behavior of a feature we're implementing. 

Such behavior is presented in form of a specification defined in a way to be understandable to all parties in the product development process, including product owners, designers, developers, QA staff as well as stakeholders).

BDD specification can have many shapes. We will be using [Gherkin syntax](https://cucumber.io/docs/gherkin/) to present a scenarios. Here is an example of one feature described by using Gherkin syntax.

```gherkin
Feature "Login"

Scenario: "Successful administrator login"
	Given that the user with administrator privileges opened a web page
	And that the user is presented with the login form
	When the user input the correct credentials
	Then user with administrator privileges should be presented with an admin page

Scenario: "Successful user login"
	Given that the user with ordinary privileges opened a web page
	And that the user is presented with the login form
	When the user input the correct credentials
	Then user with ordinary privileges should be presented with a welcome page
```

With the example above, we have described the behavior of a "Login" feature by defining two scenarios. These scenarios describe what should happen when the administrator is logged in into the app and what should happen when a user without administrative privileges is logged in into the app. 

This specification of behavior is readable to anyone, from stakeholders to QA, but it undoubtedly defines how this feature should work. 

## BDD process

The process of defining the BDD specification is usually split into three major steps:

1. Discovery

    Also known as the three amigos meeting consists of meeting with the product owner, developer, and tester to discuss the user story where usually product owner explains what needs to be done. The developer should get some examples explained by the product owner. The tester should come up with other scenarios the product owner, or developer did not come up with. 

    At the end, all three of them will come with the desired behavior of the system

2. Formulation

    This stage is about a specification definition for a feature. By knowing what has been discussed during the discovery phase,  scenarios in gherkin form should be defined.

3. Automation

    Is the implementation of the automated tests that are running based on the steps defined in the gherkin specification.

## How BDD fits into the product planning process in Shyft

Generally, the BDD discovery and formulation phase should happen as earliest as possible in the product planning process.

By looking at the flow that has been defined for Shyft - [Product Flow](https://www.notion.so/Product-Flow-5c2212fff181418cb73b3992f636e8c9) we can clearly see three major events before the feature goes into development, that is:

- Kick off
- Tech design
- Hand off

### Kick off

Is when product owner/manager presents the feature to engineering

### Tech design

Is when project management and engineering team is working on technical specifications definitions for the given feature, create sub tickets for backend, frontend, android, iOS .. and define a technical specification like HLA architecture, sequence diagrams, API specification etc.

### Hand off

Is when all specifications are completed and the feature is ready to be rolled into the planning an being prioritized. After this, the feature should be ready for the development.

By shortly explaining each of these events, we have to decide at what point the BDD discovery phase should kick in. Generally, a Kick-off meeting is something that by its definition is the same as a Discovery meeting from the BDD process. Therefore, some of the possible scenarios will be presented by the product owner during the kick-off meeting.

## ‼️ BDD discovery

Is an additional step that should happen between Kick off and the Tech design phase. 

During the BDD discovery, a project lead should do the following:

1. Define a list of possible scenarios, without going into the scenario definition
2. Communicate with the product owner and QA the list of scenarios (verbally or non-verbally), to verify that the suggested scenarios are in-line with how product sees the feature working and how QA see the corner cases.
3. Once the list of scenarios is verified and approved, these scenarios should be defined in Gherkin form. These scenarios have to be placed into the repository created for the product we are currently working on and linked as GitHub URLs into the feature tickets in Notion.
4. Upon scenario completion, the product owner and QA should be notified to verify and approve the validity of these scenarios. If everything is ok, the next stage, which is "Tech design" can start.

## How BDD fits into the development process in Shyft

In development process, we differentiate two moments related to BDD. 

1. When development team do the implementaiton
2. When QA team do the testing

### Using BDD during feature implementation

Once the developer gets the ticket for the implementation, BDD specification already should be the part of the feature that ticket belongs to. In order to do the implementation properly, a developer should:

1. Go through all scenarios defined for this feature to get the better understanding of how this feature should work and what are the corner cases we should think of.
2. Do the implementation and make sure that we have:
    - Proper unit test coverage
    - Proper integration test coverage

        If we look at the [BDD: Part 1 - Introduction](https://www.notion.so/BDD-Part-1-Introduction-9aafd4d3ef594f1599a70476a29e92c9) and the related project on GitHub

        [DejanMilicic/BddDemo](https://github.com/DejanMilicic/BddDemo)

        we will notice that BDD specifications can be turned into integration tests for the purpose of the implementation validation. This demo project is about the backend project, but in general, there are no limitations to apply the same strategy on other platforms.

3. Once the implementation and the testing are completed, the developer has to go through the implementation manually and validate that the implementation is in line with the BDD specification.

### Using BDD during QA

Ideally, when the feature goes to QA phase, it should be treated:

1. Manually, so that the QA validates the implementation and assures all of us that the implementation is without flaws. This process is aligned to BDD specification as well, as the specification is the major guideline for the QA members to follow when doing their magic of detecting the bugs.
2. Automatically. Once the manual process validates that the implementation is correct, BDD specification becomes the regression test by utilizing its scenarios and steps and implementing an automated test with the help of libraries such as SpecFlow.

[SpecFlow - Behavior Driven Development for .NET](https://specflow.org/)

Therefore, QA team will start with the implementation of the automated tests, based on the BDD specification defined for a specific feature.

However, at the moment we are not in a position of automating the BDD and we will skip the automation step of the QA consciously, building the technical debt and going back to it, once we boost the QA team numbers and experience.

### BDD as regression test

Once the feature is deployed and closed, BDD once as a specification now is a regression test which runs on a recurring basis or when required, but provide a strong confidence into the proper functioning of the feature, for a long time.