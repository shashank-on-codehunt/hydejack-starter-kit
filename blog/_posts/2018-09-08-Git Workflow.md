---
layout: post
title: Git Workflow
description: >
  Guide for Using Git workflow.While working on team we often get confused with mutliple branches and a proper managment gets lacking , however with Git Workflow we can get very productive just as team starts following a single workflow.
categories: [devlog]
tags:       [Git, Project Management]
sitemap: false
image: /assets/GitWorkflow/label.jpg
comments: true
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}
![{{ site.baseurl }}/assets/GitWorkflow/GitWorkFlowLabel.jpg]({{ site.baseurl }}/assets/GitWorkflow/GitWorkFlowLabel.jpg)

It is Adviced to open Image in separate window before reading below content, which is actually explaining the entire process.

# Handling New Feature

## Usecase ( Points in yellow)

Suppose a new Feature comes with Name Feature_3 having 3 JIRAs
to complete the Feature

1. We will first make a new Feature branch with the particular
name, commit updates according to Design as 'initial setup'
    - This may contain common classes , properties file for
    the entire process
2. Now Depending on multiple developers working we can
make multiple branches for same , Lets call them
    - Feature_3_Dev1
    - Feature_3_Dev2
3. Dev1 commits JIRA_1
4. Dev1 raises a Pull Request
5. Dev2 observes that JIRA_2 is multiple days of work and
might need multiple commits.
6. A new branch is created by Dev2 so as to handle JIRA2 with
Name Feature_3_Dev2_Jira2
7. After completing the JIRA2 with multiple commits, he merge
the JIRA_2 into his dev feature branch i.e. Feature_3_Dev2
    - This will ensure that every developer branch only
    contains commits with particular JIRAs
    - This would be helpful to track on individual Developer
    level
8. Dev2 will raise a pull request on Feature Branch
9. Raise pull request to Feature Branch, Concerned person will
make sure pull request is being resolved on Feature branch
    - It might happen that Pull Request has not being
    resolved and Dev1 commits with JIRA_3 on
    Feature_3_Dev_1
        - In that case developer should pull the
        code from Feature Branch before raising
        pull request considering that in case on
        any Merge Conflict (theirs) have
        preference
        - Or a code review can be done at this
        level
        - This will make sure that the merging at
        feature branch is not being done for same
        thing again
10. Once all Jiras are done, testing for the feature will be
done(Currently manual) , if it passes it will be passes it will
be Rebased to Development Branch
    - Rebase will allow us to track all the jiras from feature
    branch
    - Make sure to tag the last Jira with the feature tag so
    that feature can be tracked in git on development
    branch
    - In case of no issue During SIT then we can directly
    integrate in Development and production branch

# Handling Hot Fixes

## Usecase (Points in Red)

If we get any bugs or issue in Production , these are usually issues
those are needed to be fixed at earliest

- Patch_1 will be updated on hotfix branch and testing will be
done on same
- Same will be pushed to Dev branch
- After through regression test , it will be merged with
Production branch , same will be deployed on live
environment

# Handling Bugs

## Usecase (Points in Green)

If any bug is being noticed in SIT or development while testing

Note bugfix remains merged with Development branch , hence when
a commit is made for bugfix branch and then Merged with
Development branch

- A new commit is made on bugfix branch , where testing is
done
- A merge request is made on Development branch where
testing and code review would be done
- After all bug fixes and multiple iterations of step 1,2
Development branch will rebase with Production branch

# Branches

## Master/Production

present on live server or Production

## Hotfix

keeps track of Hotfixes or patches in case of urgent production issue

## Development

Development keep track of whatever is present in SB1 or
SIT currently

## Bugfix

Keeps a track of Bug fixes in case any issue is found
while testing on SIT or SB1
Usually when there is not bug the head, it remains
merged with Development branch

## Feature Branch

Keeps track of any of new Feature issue that is present

## Feature_Dev# i.e.

- Feature_1
- Feature_2

This is individual developer branch for the
particular Feature, keeps track of all the Jira
assigned for the feature ,

Note : in case of multiple commits for Jira its always
better to have individual branch for the particular JIRA

## Feature_Dev#_Jira#

- Feature_3_Dev1_Jira2

This is a Jira branch that has been spawned from the
individual Dev branch for a feature make sure that the
naming structure is as suggested above

## Rules and Restrictions

- Direct merge to Development and Production is not allowed
    - one needs to raise a merge request to do the same
- Any commit on feature branch will be made using Pull
Request from individual Developers branch
- Integration Test will be done from Development branch and
will contain tested code on SIT
- Production branch states what is presently present in
production environment

# Declaimer

- Following names have been taken randomly
    - Dev1, Dev2 should be replaced by individual names
    - Feature_3
- This process contains almost all scenarios , depending on the
scale of work one can decrease the level of complexity

