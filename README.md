## Using Jujutsu with the repository

This repository uses a colocated Jujutsu/Git workspace. The existing Git repository remains available for GitHub integration, while Jujutsu provides the local change-oriented workflow.

From the repository root, initialize Jujutsu once:

Initialize jj in colocated mode

```bash
jj git init --colocate
```

Verify the workspace:

```bash
jj git colocation status
jj status
jj log
```

The `.git` directory stores Git metadata, and the `.jj` directory stores Jujutsu metadata. The two systems share the same working copy.

A typical workflow is:

```bash
jj status
jj diff
jj describe -m "Describe the current change"
jj new
jj bookmark set main -r @-
jj git push --bookmark main
```

Jujutsu tracks working-copy changes automatically, so `git add` is normally unnecessary. Use `quarto preview` to preview the book and push the completed changes to `main` to trigger the GitHub Pages workflow.

