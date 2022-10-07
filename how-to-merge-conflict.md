[⇦ Back to: PR Update](how-to-pr-update.md) | [⇧ Overview](README.md)

# Resolving merge conflicts

> 💡 Resolving **merge conflicts** involves manually specifying what the result combining multiple commits affecting the same line(s).

Git can handle many merges automatically, even if they affect the same file, as long as they don't modify the same line in different (incompatible) ways.

## Using GitHub Desktop and an editor like VSCode

You see a warning about a merge conflict when merging branches, like this: 
<img width="1072" alt="GitHub Desktop dialog resolve conflicts before merge, 1 conflicted file (git-text-content.md), open in visual studio code." src="https://user-images.githubusercontent.com/2803227/194439101-710c075e-4662-4be4-bf97-d03096803863.png">

Depending on whether you have a compatible editor installed, GitHub desktop may offer to open the conflict in the editor.

In visual studio code, the editor shows the each of the (groups of) conflicting lines like this: <img width="552" alt="Screen Shot 2022-10-06 at 19 59 59" src="https://user-images.githubusercontent.com/2803227/194439362-d6f58961-7a8e-4101-ba9e-1ad22c4d60a5.png">

Each conflict is similarly marked.

The first part comes from your "HEAD" commit, the one you had open before you started the merge, in this case the PR's branch:
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

You need to modify the code so that includes the correct parts of all of the commits. In our case, both the removal of the `[edit]` as well as the addition of the `##` is wanted, so we resolve the commit by rewriting the part of the file to look like this:

```md

## Git server

```

... where we deleted all of the `<<<<<<< HEAD`, `=======`, and `>>>>>>> main` lines. 

You will need to fix all merge conflicts before you can successfully finish the merge.

Commit the result to complete the merge. 
