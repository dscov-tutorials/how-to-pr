[⇧ Overview](README.md)

# Branch Protection Rules
> 💡 Repository owners can set up **branch protection rules** to enforce a minimum number of approvals, to avoid people committing directly to "main" without a PR, etc. 
 
Find these in the repository Settings > Branches > Branch protection rules. <img width="1145" alt="Screen Shot 2022-10-06 at 20 34 38" src="https://user-images.githubusercontent.com/2803227/194442196-ba46a05a-4a0d-4af0-ae68-fbe6775938f8.png">

We recommend:
- **Require a pull request before merging**
  - **Require approvals**. *Required number of approvals before merging* should be 1 or more, depending on your team.
- **Require status checks to pass before merging**. This ensures that any automated build scripts have to run correctly, or syntax checkers have to pass. Many of these can be set up fairly easily using GitHub Actions.
