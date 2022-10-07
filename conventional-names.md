[⇧ Overview](README.md)

# Conventional Names

> 💡 The CCV uses **conventional names** to make issues, pull requests, branches and commits stylistically consistent and technically useful. These are based on the [**conventional commits**](https://www.conventionalcommits.org/) standard.

These conventional names have the form:
```
<type>[optional scope]: <summary>
```

The parts are:
- `<type>` is one of 
  - `feat` for a new feature which has been added, or 
  - `fix` for something which has been repaired, or 
  - a handful of other types (see [the conventional commits website](https://www.conventionalcommits.org/) for details.)
- If the change made breaks an existing interface, then an `!` is appended after the `[optional scope]`

For branches, which don't allow spaces and may include issue numbers, the convention is modified. For details see the [page about branches](how-to-branch.md).

For commits, there is a more detailed specification, which you can find on the [page about commits](how-to-commit.md).