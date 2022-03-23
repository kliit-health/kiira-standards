# Branching

We would like to follow as simple of a process as possible to allow for developers to quickly branch/develop/push their code. However, there are some differences between developing software for a mobile application that is deployed to an app store, and deploying to our cloud IT services. Thus, we can have one main strategy for all development, with some minor adjustments for mobile apps.

## Primary Branching Strategy

Default branch is `main`

- Create feature branch `JIRA-###/short-description` from `main` branch
    - This branch can either be for one Jira story, or for an epic, which would include multiple stories
    - If multiple people are working on this feature, and/or there are multiple smaller branches, just PR those branches into the larger feature branch
- Develop on feature branch
- Create a Pull Request to merge the feature branch into the main branch
    - The PR will trigger a deployment to the **development** environment
    - Manual approval step for deploying to **qa/staging** environment
- Test on the **qa/staging** environment
    - Manual approval step for **approving** the branch
- Approve PR and merge into main branch
    - PR approval will trigger a deployment to the **production environment**

## Mobile App Branching Strategy

Strategy is basically the same as above, except there’s always a release branch that should contain everything that will go into the mobile app release.

- Create release branch `releases/v#.#.#` or `hotfixes/v#.#.#` branch from `main` branch
- Create feature branch(es) `JIRA-###/short-description` from the release branch
- Develop on feature branch
- Create a Pull Request to merge the feature branch into the release branch
    - The PR will trigger a deployment to the **development** environment
- Approve the PR and merge into the release branch
- Create an APK from the release branch
- Test
- Create a Pull Request to merge the release branch into the main branch
- Approve the PR and merge into the main branch
- Tag the main branch with the release version
- Create artifacts from tagged commit on `main` and submit to Apple and Google Play stores