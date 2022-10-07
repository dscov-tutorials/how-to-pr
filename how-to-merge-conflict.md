[⇦ Back to: PR Update](how-to-pr-update.md) | [⇧ Overview](README.md)

# Resolving merge conflicts

Git can handle many merges automatically, even if they affect the same file, as long as they don't modify the same line in different (incompatible) ways. If it can't then it's up to you.

> 💡 Resolving **merge conflicts** involves manually specifying what the result combining multiple commits affecting the same line(s).

To handle the merge conflicts you need to:
- locate them
- fix each of them in turn
- commit the result

## Locating merge conflicts
### Using GitHub Desktop and an editor like VSCode

You see a warning about a merge conflict when merging branches, like this: 
<img width="1072" alt="GitHub Desktop dialog resolve conflicts before merge, 1 conflicted file (git-text-content.md), open in visual studio code." src="https://user-images.githubusercontent.com/2803227/194439101-710c075e-4662-4be4-bf97-d03096803863.png">

Depending on whether you have a compatible editor installed, GitHub desktop may offer to open the conflict in the editor. Click on that.

If you click on the button, the editor shows the each of the (groups of) conflicting lines like this: <img width="552" alt="Screen Shot 2022-10-06 at 19 59 59" src="https://user-images.githubusercontent.com/2803227/194439362-d6f58961-7a8e-4101-ba9e-1ad22c4d60a5.png">

### Using GitHub

In the PR, if there are conflicts with the base branch, you may see a dialog like this: <img width="507" alt="Screen Shot 2022-10-06 at 20 10 46" src="https://user-images.githubusercontent.com/2803227/194440335-f1607acb-efed-47a5-9923-66b257006d3f.png">

Click on the button to see the merge conflict, each of which will look something like this:
<img width="938" alt="Screen Shot 2022-10-06 at 20 12 59" src="https://user-images.githubusercontent.com/2803227/194440382-4a890a35-c52c-413f-9da8-9f40a865eb9d.png">

### Using `git` on the command line

Find unmerged files by running
```shell
git status
```

...to show something like this:<img width="638" alt="Screen Shot 2022-10-06 at 20 17 51" src="https://user-images.githubusercontent.com/2803227/194440838-eab53116-53ef-4b97-9a37-3d9860951848.png">

The files under "Unmerged paths:" have merge conflicts to fix. Open them in your text editor.

## Fixing the merge conflicts

A merge conflict looks something like this:
```md
<<<<<<< HEAD
Git server
=======
## Git server[edit]
>>>>>>> main
```

The first part contains the code from your "HEAD" commit, the one you had open before you started the merge, in this case the PR's branch:
```md
<<<<<<< HEAD
Git server
=======
```

The second part is the other commit which you are merging in. In this case, it comes from the main branch:

```md
=======
## Git server[edit]
>>>>>>> main
```

You need to modify the code so that includes the correct parts of all of the commits. 

In the example, both the removal of the `[edit]` as well as the addition of the `##` is wanted, so I resolve the commit by rewriting the part of the file to look like this:
```md
## Git server
```

... where all of the `<<<<<<< HEAD`, `=======`, and `>>>>>>> main` delimiters were deleted. 

You will need to fix all merge conflicts in all files before you can successfully finish the merge.

Commit the result in the usual way to complete the merge. 

## Abort the merge

If you can't successfully complete the merge, you can "abort" it, rolling back your changes and getting back to the clean state from before, as follows.

### Using GitHub

Just leave the merge page.

### Using GitHub Desktop
Click the "Abort Merge" button:<img width="1072" alt="Screen Shot 2022-10-06 at 20 23 48" src="https://user-images.githubusercontent.com/2803227/194441354-c081b236-bbc7-4a59-ab1f-df38f604e87e.png">

### Using `git` on the command line
You can try to revert a merge with conflicts by running:
```shell
git merge --abort
```

> ⚠️ **Not all merges can be aborted**. From the [Git documentation on `git merge`](https://git-scm.com/docs/git-merge):
> `git merge --abort` will abort the merge process and try to reconstruct the pre-merge state. However, if there were uncommitted changes when the merge started (and especially if those changes were further modified after the merge was started), `git merge --abort` will in some cases be unable to reconstruct the original (pre-merge) changes. Therefore:
>
> Warning: Running `git merge` with non-trivial uncommitted changes is discouraged: while possible, it may leave you in a state that is hard to back out of in the case of a conflict.
