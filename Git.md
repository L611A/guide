# Git

Here you can find everything you need to know about **Git** workflow.

## Branching + Pull requests (PRs)

Knowing the branching and pull request conventions is crucial and you will find everything about them in this section.

### `master` and `development`

In a typical repository, there are two main branches: `master` branch and `development` branch. The `master` branch contains the most up-to-date production build and is merged with `development` to once changes in `development` are ready for deployment.

### Feature branching

Never branch from `master`; always branch from `development` or another branch that branched from `development`. A branch typically means another feature in progress. Create a branch of `development` called `my-feature` by using:

```bash
git checkout -b my-feature development
```

#### Branch naming conventions

The name of a branch should be meaningful; others who are new to the repository should know what your branch is for, so we have imposed a simple naming convention for branches in all organization-wide repositories.

Always derive the name of a branch from the following: `parent-branch/feature-name`. If I'm fixing a bug found in the `development` branch, I create a branch named `development/major-bug-fix`.

### Merging branches

Before merging, please be sure to check if the parent branch has been previously updated. If it was actually updated, the continuity of your branch needs to be updated, or *rebased*.

When you complete your feature or any type of work on a branch and is ready to be merged into the parent branch, submit a **pull request** that describes what you have done and documents the major revisions made to the code. Please also to be sure to request code reviews from the people in charge of the repository!

When changes are approved by all reviewers, the branch will be merged. Otherwise, fix what needs to be fixed and request for another review.

#### Merge conflicts

When submitting a pull request, there very well may be *merge conflicts*. This could be the result after *rebasing*. First, try your best to fix your code around the merge conflict. If there is no way around, please consult the author of the code that your branch has conflict with and make the proper adjustments and revisions. Make sure any changes to that code is approved by all parties involved.
