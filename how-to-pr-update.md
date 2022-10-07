[⇦ Back to: Clean up](how-to-clean-up.md) | [⇧ Overview](README.md) | [**⇨ Next: Merge Conflict**](how-to-merge-conflict.md)

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
<img width="455" alt="Screen Shot 2022-10-06 at 19 48 44" src="https://user-images.githubusercontent.com/2803227/194438225-31ec29cd-d0ab-4823-8f0b-0ee40931af31.png">

If there are conflicts, it will offer you the option to resolve the merge conflicts (covered in the next section). 
<img width="836" alt="Screen Shot 2022-10-06 at 19 46 24" src="https://user-images.githubusercontent.com/2803227/194438004-d394cf27-93ab-4fa3-9f7d-b06ea0a301f9.png">

> 💡 Repository Admins can go into the repository Settings and activate the option "Always suggest updating pull request branches", to show an "update branch" button at the bottom of the pull-request, for cases when "main" has been updated. <img width="914" alt="Screen Shot 2022-10-06 at 19 49 49" src="https://user-images.githubusercontent.com/2803227/194438340-d367d69d-dc23-40fa-9daf-17ae0b1612d4.png">


### Using GitHub Desktop
Ensure you have the latest version of the main branch by clicking "Fetch origin" <img width="1028" alt="Screen Shot 2022-10-06 at 18 35 18" src="https://user-images.githubusercontent.com/2803227/194431428-a7bd6848-459d-40b9-bd46-cdc45ce63a87.png">

Open the branches menu, and click "Choose a branch to merge into <your-branch-name> <img width="1072" alt="Screen Shot 2022-10-06 at 18 35 27" src="https://user-images.githubusercontent.com/2803227/194431467-e7b574e1-555f-48e0-95b7-63201351f10e.png">

Depending on whether or not the branches conflict, you will see a warning about a merge commit, or none.

  <table border="0">
    <tr>
      <td>
<img width="1072" alt="Screen Shot 2022-10-06 at 18 35 55" src="https://user-images.githubusercontent.com/2803227/194437226-47479fe5-185d-42e4-a3a1-cc0c6498a34b.png" />
      </td>
      <td>
  <img width="1072" alt="Screen Shot 2022-10-06 at 18 35 34" src="https://user-images.githubusercontent.com/2803227/194437241-569f4cec-9fa1-4c7f-877c-49cbf14fdd2b.png" />
      </td>
    </tr>
  </table>
  
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
