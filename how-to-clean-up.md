# Clean up after yourself
> 💡 Repository owners can set the **automatically delete head branches** setting in the repository settings. This ensures that pull request branches are automatically deleted (but recoverable) after merging.

Once you've merged your PR, the branch (a pointer to the last commit before the merge) still exists. You can end up with hundreds or thousands of these "stale" branches with no useful function in a long project, which can make keeping track of the current branches more challenging.

You can delete the branches as follows:

## Using GitHub (strongly recommended)

Open the branches list from the repository page:<img width="977" alt="Screen Shot 2022-10-06 at 21 21 21" src="https://user-images.githubusercontent.com/2803227/194446465-4565eda0-1131-4aba-8340-39a8481ed4cd.png">

For each branch you want to remove, click on the trashcan symbol: <img width="977" alt="Screen Shot 2022-10-06 at 21 22 02" src="https://user-images.githubusercontent.com/2803227/194446519-7c99fd4d-2bc6-405a-87b2-245dde9b0be1.png">

You can go back to the branch list to recover the branch if deleted in this way:
<img width="842" alt="Screen Shot 2022-10-06 at 21 26 44" src="https://user-images.githubusercontent.com/2803227/194446950-9189dde8-3424-4242-9e93-5704cc554a24.png">

## Using GitHub Desktop
In the branch list, right click the *remote* branch and click "delete". <img width="1043" alt="Screen Shot 2022-10-06 at 21 24 13" src="https://user-images.githubusercontent.com/2803227/194447013-9d306195-a6df-401c-9118-25c47382bcbe.png">

Click through the warning.
<img width="1028" alt="Screen Shot 2022-10-06 at 21 24 17" src="https://user-images.githubusercontent.com/2803227/194447069-96f9a67b-f20d-49f2-8c8a-f70c0b0766ee.png">

> ⚠️ The branch is then removed on GitHub without the ability to restore it:
> <img width="977" alt="Screen Shot 2022-10-06 at 21 28 56" src="https://user-images.githubusercontent.com/2803227/194447171-0d64da8e-65e4-47d6-93ac-08c8f32e62f5.png">

## Using `git` on the command line
To delete a remote branch, run:
```shell
git push origin --delete <your-branch-name>
```

e.g. `git push origin --delete format-external-links-heading`. 

> ⚠️ Like in GitHub desktop, this removes the branch without the ability to restore it.