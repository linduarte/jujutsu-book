# Learning Jujutsu (jj) - Step-by-Step Guide

**Modern Workflow with `jj git init --colocate`**

Act like an expert teacher and skill coach. This guide breaks the topic into 5 clear difficulty levels.

## Level 1: Complete Beginner

**What you should understand at this stage:**  
Jujutsu (jj) is a modern version control system that works seamlessly with Git. It uses a "change-centric" model where your working copy is always a real commit (no separate staging area like Git's index). Changes to files are automatically snapshotted into the current change. You start with `jj git init --colocate` for a hybrid setup that keeps full Git compatibility.

**What mastery looks like at this level:**  
You can initialize a repo, make simple file changes, see your status, describe what you're doing, and create new changes without panic. You feel safe experimenting because everything is tracked.

**The most important concepts or skills to focus on:**  
- Installing jj and running `jj git init --colocate` (or `jj git clone --colocate`).  
- `jj status` (or `jj st`), `jj log`, `jj diff`.  
- The working copy `@` is always a commit.  
- `jj new -m "description"` to start a new change.  
- `jj describe` to add/edit a message.  
- Automatic tracking of changes (no `git add` needed usually).

**One milestone that proves you are ready to move forward:**  
You have a working local repo with 2-3 changes in your history, visible in `jj log`, and you understand why the working copy changes its commit ID but keeps a stable change ID.

**One hands-on exercise or mini-project:**  
1. Create a new directory, `cd` into it.  
2. Run `jj git init --colocate`.  
3. `jj new -m "Add hello world"`, create `hello.py` with some code.  
4. `jj status`, `jj diff`, `jj new -m "Add README"`, add a README.  
5. Explore `jj log`.

**Common mistakes learners make at this level:**  
- Forgetting to run `jj new` and thinking you're "staging" like Git.  
- Ignoring the difference between change ID (stable) and commit ID (changes on rewrite).  
- Trying Git commands that conflict with jj's automatic snapshots.

**A simple self-check question before moving to the next level:**  
What does `jj st` show after you edit a file in the working copy, and why didn't you need to `add` it?


## Level 2: Basic Understanding

**What you should understand at this stage:**  
Changes evolve (mutable until shared/pushed), while the repo history is built from them. You can move between changes, amend, and start fresh ones. The operation log (`jj op log`) lets you undo almost anything.

**What mastery looks like at this level:**  
You routinely create descriptive changes upfront, edit files, move to the next task cleanly, and recover from small mistakes using undo or evolog.

**The most important concepts or skills to focus on:**  
- `jj new` (with or without parent), `jj describe`.  
- `jj squash` (amend-like for current change).  
- `jj edit <change>` to resume editing an older change.  
- `jj undo`, `jj op log`, `jj op restore`.  
- Basic `jj log` navigation and the `@` symbol for working copy.  
- `jj diff` and understanding evolog (`jj evolog`) for change history.

**One milestone that proves you are ready to move forward:**  
You can start a change, make edits, decide it's incomplete, `jj new` to the next task, then go back and `jj squash` or `jj edit` to refine the previous one.

**One hands-on exercise or mini-project:**  
Build a small script project (e.g., a Python CLI tool). Create changes like "Initialize project structure", "Add core function", "Add CLI entrypoint". Use `jj new -m "..."` upfront. Practice squashing a small fix into the first change.

**Common mistakes learners make at this level:**  
- Over-editing one massive change instead of breaking into logical ones.  
- Forgetting to describe changes early.  
- Relying too much on Git commands before learning jj equivalents.

**A simple self-check question before moving to the next level:**  
How do you safely experiment with a change and then either keep it or discard parts? Can you show `jj op log` to undo a bad `jj new`?


## Level 3: Practical User

**What you should understand at this stage:**  
Branch-like workflows use bookmarks (jj's lighter alternative to Git branches). You push/pull with Git interop, handle simple rebases, and manage small stacks of changes.

**What mastery looks like at this level:**  
Daily workflow feels smoother than Git: you create stacked changes for features, push to GitHub, update from remote, and resolve basic conflicts without stress.

**The most important concepts or skills to focus on:**  
- Bookmarks: `jj bookmark create <name>`, `jj bookmark set`, `jj git push`.  
- `jj git fetch`, syncing with remotes.  
- Rebasing: `jj rebase -s <source> -o <onto>`.  
- `jj abandon` for discarding changes.  
- Revsets basics: `@`, `@-`, `::@`, etc. for `jj log -r`.  
- Conflict resolution with `jj resolve` or manual editing + `jj squash`.

**One milestone that proves you are ready to move forward:**  
You clone a Git repo with jj, make 3-4 stacked changes, push them, fetch updates, and rebase your stack cleanly.

**One hands-on exercise or mini-project:**  
Contribute to a small open-source repo or your own: implement a feature in 2-3 small changes, push, simulate a remote update, rebase, and resolve any conflicts.

**Common mistakes learners make at this level:**  
- Treating bookmarks exactly like Git branches.  
- Pushing before changes are ready.  
- Ignoring conflicts and not using `jj new` on conflicted parents.

**A simple self-check question before moving to the next level:**  
Explain how to move a change "back in time" or reorder your stack. What command shows the full history including remote bookmarks?


## Level 4: Problem Solver

**What you should understand at this stage:**  
Advanced history editing, revsets for powerful queries, absorbing changes, splitting, and working with larger stacks or team workflows. You leverage the operation log for safety.

**What mastery looks like at this level:**  
You confidently rewrite local history (squash, split, move changes), debug with revsets, handle merge conflicts in stacks, and integrate with GitHub PRs.

**The most important concepts or skills to focus on:**  
- Advanced revsets: `foo::`, `foo..bar`, functions like `bookmarks()`, `trunk()`.  
- `jj absorb`, `jj split`, `jj move`.  
- `jj evolog`, detailed `jj show`.  
- Stacked PRs and updating them.  
- `jj git push --all` or selective.  
- Resolving complex conflicts.

**One milestone that proves you are ready to move forward:**  
You take a messy branch with 5+ changes, clean it into logical commits using squash/split/move/absorb, rebase onto latest trunk, and push a clean stack.

**One hands-on exercise or mini-project:**  
Refactor a small codebase (add tests, rename, extract functions) across multiple files/changes. Use jj tools to reorganize the history into a polished sequence.

**Common mistakes learners make at this level:**  
- Overusing complex revsets before mastering basics.  
- Forgetting immutable commits (published ones).  
- Not checking `jj op log` before destructive operations.

#### A simple self-check question before moving to the next level:  
#### How would you find all changes touching a specific file? Or absorb scattered edits into the right changes?


## Level 5: Confident Practitioner

**What you should understand at this stage:**  
Full power of jj's model: changes vs. revisions, mutable history locally with safe undo, Git interop, customization, and team best practices.

**What mastery looks like at this level:**  
Fluid, intentional development. You maintain clean histories, handle large refactors effortlessly, and use it daily as your primary VCS.

**The most important concepts or skills to focus on:**  
- Config customization, aliases, revset aliases.  
- Advanced workflows (edit vs. squash, large stacks).  
- Performance with big repos.  
- Collaboration patterns: stacked diffs, code review.  
- Deep operation log usage.  
- When to use native jj backend.

**One milestone that proves you are ready to move forward:**  
You migrate a medium-sized Git project fully, set up team conventions, and comfortably mentor others on jj.

**One hands-on exercise or mini-project:**  
Set up a personal or team project with jj best practices. Tackle a non-trivial refactor using all tools.

**Common mistakes learners make at this level:**  
- Premature optimization.  
- Not sharing knowledge with the team.  
- Ignoring upstream changes in long-lived stacks.

##### A simple self-check question before considering yourself advanced:  
##### Design a workflow for a feature that requires parallel experiments, then merging the best parts. How does jj's model make this easier?

