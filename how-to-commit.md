[⇦ Back to: Branch](how-to-branch.md) | [⇧ Overview](README.md) | [**⇨ Next: Push**](how-to-push.md)

# Solve the issue, commit-by-commit

> ## Definitions
> 💡 A **commit** is a snapshot of all the files in the repository.
> 
> 💡 Commits are listed in the **log** 

## Approach

- Make a small change, making an improvement.
- Commit it (see below for details for your Git Client):
  - Add the files which you want to update
  - Add a summary of 50 characters or fewer, e.g. 
    - "fix: remove warning about citations in Characteristics section" or 
    - "feat: add new list of maintainers in overview". ("feat" is short for "feature". See [Advanced Commit Messages](#advanced-commit-messages) for more details.)
  - (Optionally) add a more detailed description.
- Repeat until you've made the **minimum number of commits** which make sense for someone else to review and merge into the repository. This will be your "pull request."


> 💡 **Commit pro-tips**:
> - A good commit does exactly one thing. 
> - Making several tiny commits each couple of minutes is normal (and often good).
> - Try to make commits which retain the internal consistency of the document, e.g. replacing a noun with a synonym throughout a paragraph or document.


## Using GitHub Desktop
GitHub Desktop automatically recognizes that you've made a changes to the files.
<img width="1072" alt="Screen Shot 2022-10-05 at 17 02 03" src="https://user-images.githubusercontent.com/2803227/194164478-218c4046-2769-45dd-8d06-102f5d2b4ac0.png">

Add your commit summary and optional description in the field at the bottom left, and then press "commit to 12-your-branch-name-here".

The commit will appear in the log, shown on the "history" tab.
⛔️TODO⛔️: add image here (screenshot 08:34)

## Using `git` on the command line

Git needs to be told which of your files have been modified. "Stage" these files using the command `git add <filename>`, e.g.

```shell
git add git-text-content.md
```

To see a list of modified files and whether they are staged (*i.e.* going to be included in the next commit), run:

```shell
git status
```

<img width="682" alt="Screen Shot 2022-10-05 at 17 32 49" src="https://user-images.githubusercontent.com/2803227/194168104-b12b4b6a-a14c-4ae0-8a47-530f97d9cf7e.png">

Commit all of the staged files add add the commit **m**essage by running:
```shell
git commit -m "<your commit message here>"
```

If you want to include a longer description, run:
```shell
git commit -m "<your commit summary here>

<longer description here>
"
```

Once you've committed, check the log to see your commit:
```shell
git log
```

Press "q" to exit the log.

## Advanced Commit Messages

💡 The CCV uses [conventional commits](https://www.conventionalcommits.org/) to make commit messages stylistically consistent and more technically useful.

Conventional commit messages have the form: 
```
<type>[optional scope]: <summary>

<description>

<footer>
```

- `<type>` is one of 
  - `feat` for a new feature which has been added, or 
  - `fix` for something which has been repaired, or 
  - a handful of other types (see [the conventional commits website](https://www.conventionalcommits.org/) for details.)
- `[optional scope]` is the part of the project which has been modified. In our case, this could be the section heading in the Wikipedia document. The scopes should be agreed upon within a project.
- `<description>` should tell the reader, familiar with the project, what was changed, and should make it easier to locate a particular commit you may wish to revert at a later time, 
- If the change made breaks an existing interface, then 
  - an `!` is appended after the `[optional scope]`, or 
  - `BREAKING CHANGE: <details>` is added in the `<footer>`.
- The `<footer>` may also include keywords referencing issues and PRs from GitHub. See [the GitHub Docs on keywords](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests) for details.