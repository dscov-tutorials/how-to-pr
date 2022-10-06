[⇦ Back to: PR](how-to-pr.md) | [⇧ Overview](README.md) | [**⇨ Next: Merge Conflict**](how-to-merge-conflict.md)

# How to update your Pull Request

Reasons you might want to update a pull request include:
- Addressing comments and requested changes
- The main branch has changed

These two cases are dealt with differently.

## Addressing comments and requested changes

Wait until you have the amount of feedback you need.

- If your PR is approved by everyone, congratulations!
- If not, and once you've got the feedback you want, then 
  - 🛠 fix any shortcomings on the *same branch*, [making new commits](), and then
  - push the updated branch using `git push` when you're done.
- **Important:** Ensure you re-request the review from your reviewers once you're finished with the updates. <img width="327" alt="Screen Shot 2022-10-06 at 17 56 46" src="https://user-images.githubusercontent.com/2803227/194426013-d5bcd4c8-2af2-4f74-8ebe-6b52c3f8b710.png">

## Merging changes from main

If another PR is merged into main before yours, you can update your branch. 

If someone else has changed how a piece of code works, it's good to check that your changes still work with the other person's update, or whether you need to make new changes yourself.

### Using GitHub

If there are no conflicts detected, then the pull request will show this at the bottom:
#########

If there are conflicts, it will offer you the option to resolve the merge conflicts (covered in the next section). 
#########

> 💡 Repository Admins can go into the repository Settings and activate the option "Always suggest updating pull request branches", to show an "update branch" button at the bottom of the pull-request, for cases when "main" has been updated. ########### 

### Using GitHub Desktop
TODO #########

### Using `git` on the command line

You can update the branch by merging as follows.

First, switch to the main branch:
```shell
git switch main
```

Ensure you have the most up to date version of "main":
```shell
git pull origin main
```

Then switch to your branch: 
```shell
git switch <your-branch-name>
```

Merge the changes from main:
```shell
git merge main
```

If necessary, [deal with any merge conflicts](how-to-merge-conflict.md) and commit the merged code.

Then update the version of the branch on GitHub:
```shell
git push -u origin <your-branch-name>
```