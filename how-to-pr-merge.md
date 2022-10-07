# Merge a Pull Request, Split It or Close It

## If Approved, Then Merge
Once you've been given feedback and it's agreed that your PR is good to be merged into the main branch, it can be merged.

You or someone with the right to write to the repository can click the "Merge pull request" button in the GitHub Pull Request.
<img width="725" alt="Screen Shot 2022-10-06 at 20 39 47" src="https://user-images.githubusercontent.com/2803227/194442629-4a867bee-91b5-4cb6-af9d-8f0caa4e51cb.png">

It is also possible to carry out merges using the GitHub Desktop application, or the command line, but these may not work if the base branch is protected (see next section). We recommend using the web interface.

## If Not, Then Close

If the people working on the project think that a PR shouldn't become part of the main branch for whatever reason, then you can close the PR without merging.

Add a comment, then click "Close with comment". The PR stays in the list of closed PRs, and you can always revisit the conversation and the code associated with it. <img width="710" alt="Screen Shot 2022-10-06 at 20 48 18" src="https://user-images.githubusercontent.com/2803227/194443371-93dca0d8-bbe5-4fe2-b282-e66b99889d3f.png">

## If PR Needs Splitting, then Split It (Before Closing It)

Some PRs need splitting into several smaller PRs before they can be properly reviewed and merged. 

If the commits were small enough, this is often extremely quick to achieve using the "cherry-pick" function of Git. In this mode, each commit is treated as a "delta" – the small change it applied to the code from before.

We recommend using the GitHub Desktop GUI for this, as selecting commits from the log can be more time consuming.

- Start a new branch from "main".
- Go through the commit history from oldest to newest, locating each of the commits which should be included in the new PR. 
  - For each, right click on it and select "Cherry-pick commit" <img width="1093" alt="Screen Shot 2022-10-06 at 20 57 44" src="https://user-images.githubusercontent.com/2803227/194444275-d6d2ddac-efbe-4124-a86b-7d112f7d8b6e.png">
- Check that the result continues to work as you had expected.

Repeat for any other branches you would like to split out from the original PR.

Then close the PR as above.

# Branch Protection Rules
> 💡 Repository owners can set up **branch protection rules** to enforce a minimum number of approvals, to avoid people committing directly to "main" without a PR, etc. 
 
Find these in the repository Settings > Branches > Branch protection rules. <img width="1145" alt="Screen Shot 2022-10-06 at 20 34 38" src="https://user-images.githubusercontent.com/2803227/194442196-ba46a05a-4a0d-4af0-ae68-fbe6775938f8.png">

We recommend:
- **Require a pull request before merging**
  - **Require approvals**. *Required number of approvals before merging* should be 1 or more, depending on your team.
- **Require status checks to pass before merging**. This ensures that any automated build scripts have to run correctly, or syntax checkers have to pass. Many of these can be set up fairly easily using GitHub Actions.
