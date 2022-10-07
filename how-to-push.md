[⇦ Back to: Commit](how-to-commit.md) | [⇧ Overview](README.md) | [**⇨ Next: Create Pull Request**](how-to-pr.md)

# Push the branch

You can share your branch (and all of the commits required to recreate its history) by **push**ing it to GitHub.

## Using GitHub Desktop

Click the "Publish Branch" button at the top of the UI
<img width="682" alt="Screen Shot 2022-10-07 at 08 46 57" src="https://user-images.githubusercontent.com/2803227/194583828-f6b886cd-2fda-4b3c-b4d0-6fa6a2f0a45f.png">


## Using `git` on the command line

Switch to the branch you would like to push:
```shell
git switch branch-you-want-to-push
```

Check you're on the correct branch by running and checking the output from:
```shell
git status
```

Once you're on the correct branch, push it by running:
```shell
git push -u origin
```

> 💡 `-u` means "set the **u**pstream branch for `git pull` and `git status`." 
> - Whenever you run the command `git pull` in future, `git` will automatically pull from the remote branch you created. 
> - Similarly, when you run `git status`, `git` will check whether your local branch is up-to-date with this remote branch.
