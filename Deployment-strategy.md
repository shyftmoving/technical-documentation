The most important thing about deployment is that we differentiate between branch and environment.  
In our organization, we have only two longterm branches: `development` and `master/main`. However, we have much more environments we work with, such as: `dev`, `qa`, `staging`, `demo` and `production`.

## Environments

### dev
**Description**: High-frequency deployment environment.  
**Used by**: Developers and QA team.  
**Purpose**: Developers to verify the functionality of the features.  
**Deployed**: From `dev` branch on every commit.  

### qa
**Description**: High-frequency deployment environment.  
**Used by**: QA team.  
**Purpose**: QA team to assure the quality once the dev team complete its work on a feature.  
**Deployed**: From `dev` branch on every commit.  

### staging
**Description**: Low frequency deployment environment. Staging environment is a pure replica of production. Only difference between `production` and `staging` is in domain.  
**Used by**: QA team.  
**Purpose**: QA team to assure the quality of the features in a production like environment.  
**Deployed**: From `release` and `hotfix` branches, on every commit.

### demo
**Description**: Very low deployment frequency environment. Deployment to demo has to be scheduled upfront, as we don't want to interrupt a current presentation of the product. Demo environment is a pure replica of production. Only difference between `production` and `demo` is in domain.  
**Used by**: Stakeholders and the sales.  
**Purpose**: To present the features to potential clients.  
**Deployed**: From `master/main` manually.

### production
**Description**: Low deployment frequency environment.  
**Used by**: Publicly.  
**Purpose**: Providing developed services to our users.  
**Deployed**: From `master/main` on every commit.

## How to deploy?

As we have different environments, and obviously different deployment frequencies, we have to have a different approaches to deployments as well. Check out the documents below:  
- [Deploy to dev](Releasing-to-dev-and-qa-environment)
- [Deploy to qa](Releasing-to-dev-and-qa-environment)
- [Deploy to staging](Releasing-to-staging-environment)
- [Deploy to demo](Releasing-to-demo-environment)
- [Deploy to production](Releasing-to-production-environment)