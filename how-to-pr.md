[⇦ Back to: Push](how-to-push.md) | [⇧ Overview](README.md) | [**⇨ Next: Review Pull Request**](how-to-pr-review.md)

# Create a Pull Request (PR)

> ## Definitions
> A **Pull Request (PR)** says “I want to merge these changes into our project. What do you think?” 

The process of making a PR is:
- Push your commit(s) to a GitHub repository.
- Create a new pull request for that branch on the  [GitHub Pull Requests page](https://github.com/brown-ccv/dscov-github-workshop/pulls).

## Make a Draft Pull Request

- Open the [GitHub Pull Requests page for the shared repository](https://github.com/brown-ccv/dscov-github-workshop/pulls).
- Click on "New pull request"
- Choose the branches to compare:
  - Select base: main (this should be the default)
  - Select compare: your-new-branch
- Add the title
- Add a description
- Add a reference to the issue you're fixing by typing "#" and then a keyword from the issue; select the correct issue from the list
- Add a few reviewers (2-5 is a good number, including at least one owner of the repository and at least one peer. Try the person next to you in the room or on Zoom.)

On the "create pull request" button, there is an arrow. Click this, and select "Draft pull request."
⛔️TODO⛔️ Image of Draft PR

## Check everything

At this stage, you can check that everything is in place.

If you realise you need to do more work on the code, then [make some more commits on the same branch](how-to-commit.md) and push them using GitHub Desktop or `git push`. The PR will update automatically.

## Mark the Pull Request as "Ready for review"

When you click "ready for review" at the bottom of the pull request conversation, the reviewers will be informed that you've requested their review.
⛔️TODO⛔️ Image of "read for review button"

At this stage, it's best to not make any more updates until the reviewers are finished and have given their feedback. It can be frustrating for the reviewer if the code changes during their review.

If you realise that the code needs updating more, then re-mark the PR as a draft. Your reviewers will be able to see that the PR is no longer ready for review. 
⛔️TODO⛔️ Image of Switch back to Draft PR

## Wait for feedback
Wait until you have the amount of feedback you need.
