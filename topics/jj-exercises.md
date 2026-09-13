# Jujutsu (jj) Exercises - By Level

**Use these alongside the main guide. Increase difficulty progressively.**

## Level 1: Complete Beginner (3 Exercises)

1. Initialize a new repo with `jj git init --colocate`. Create your first change using `jj new -m "Initial setup"` and add a README.md

2. Edit files in the working copy, run `jj st` and `jj diff`, then create a second change with `jj new`.

3. Explore history with `jj log` and modify a description with `jj describe`.

## Level 2: Basic Understanding (5 Exercises)

1. Create a change, make edits, then `jj new` to start the next one.

2. Return to the previous change and `jj squash` a fix into it.

3. Use `jj edit` on an older change and amend it.

4. Intentionally make a small mistake and recover with `jj undo` + check `jj op log`.

5. Use `jj evolog` to inspect how a change evolved.

## Level 3: Practical User (7 Exercises)

1-2. Create and push a small stack of 2-3 changes using bookmarks

3. Fetch remote updates and rebase your local stack.

4. Intentionally create a merge conflict and resolve it.

5. Manage bookmarks (`jj bookmark` commands).

6. Abandon an unwanted change.

7. Use basic revsets in `jj log -r` to filter history.

<hr style="page-break-before: always;">

## Level 4: Problem Solver (9 Exercises)

1-3. Practice `jj absorb`, `jj split`, and `jj move` on test changes

4-6. Write and use simple revsets to select and operate on groups of changes.

7-8. Rebase a stack with multiple conflicts and resolve them cleanly.

9. Take a messy local history and reorganize it into clean logical commits.

## Level 5: Confident Practitioner (12 Exercises)

1-4. Customize jj config, create useful aliases, and define revset aliases.

5-7. Work with larger stacked changes and simulate stacked PR updates.

8-9. Practice team collaboration scenarios (merges, reviews).

10-11. Optimize for a larger repo (ignore patterns, performance checks).

12. Document your preferred jj workflow in a README and "teach" it (write notes or explain to someone).

**Tip:** After each level, run `jj log` and share output here for review. Progress one level at a time!