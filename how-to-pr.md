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
- Add a reference to the issue you're fixing by typing "closes #"[^1] and then a keyword from the issue; select the correct issue from the list
- Add a few reviewers (2-5 is a good number, including at least one owner of the repository and at least one peer. Try the person next to you in the room or on Zoom.)

[^1]: See the full list of keywords like "closes" here: https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests

On the "create pull request" button, there is an arrow. Click this, and select "Draft pull request."
![Screen Shot 2022-10-06 at 15 48 42](https://user-images.githubusercontent.com/2803227/194414058-fc88ff76-4297-4699-bfce-6bc787e549fd.png)


## Check everything

At this stage, you can check that everything is in place.

If you realise you need to do more work on the code, then [make some more commits on the same branch](how-to-commit.md) and push them using GitHub Desktop or `git push`. The PR will update automatically.

## Mark the Pull Request as "Ready for review"

When you click "ready for review" at the bottom of the pull request conversation, the reviewers will be informed that you've requested their review.
![Screen Shot 2022-10-06 at 15 49 23](https://user-images.githubusercontent.com/2803227/194414124-86af1cd6-7ef3-469d-a73b-7756e167c19a.png)


At this stage, it's best to not make any more updates until the reviewers are finished and have given their feedback. It can be frustrating for the reviewer if the code changes during their review.

If you realise that the code needs updating more, then re-mark the PR as a draft. Your reviewers will be able to see that the PR is no longer ready for review. 
![Screen Shot 2022-10-06 at 15 50 11](https://user-images.githubusercontent.com/2803227/194414248-56d4136a-bb05-46bd-989b-eab134659110.png)
