# Contributing

This guide is for anyone interested in contributing to Tessel.

## Feature Requests
To request a change in any components of the Tessel ecosystem such as adding a command line interface option, adding support for various drivers in the kernel, or suggesting a new piece of hardware, please create a new post on the [Forums with the `contributing` tag](https://forums.tessel.io/c/contributing). We have no specific format for the RFC but feel free to check out [this example](https://forums.tessel.io/t/wifi-api-from-js-for-the-cc3000/399). The community will then discuss the change and if a Collaborator approves of the RFC, they will create an issue on the appropriate repository. If you agree to it, you may be assigned to the issue and expected to develop that feature.

## Bug Reports
Every once in a while, you may run into a bug when using Tessel. Please do report it! If you aren't sure where to report it (system overview coming soon!), please ask on the [Forums](forums.tessel.io) or just open an issue on this github repo (a Collaborator will move the issue if necessary). It's much preferred to report an issue that may already exist rather than risk leaving the flaw unexposed.

Opening an issue is as easy as following [this
link](https://github.com/technicalmachine/tessel-project/issues) and filling out the fields.
Bug reports should have a structure similar to (borrowed from rust-lang):

    <short summary of the bug>

    I tried this code:

    <code sample that causes the bug>

    I expected to see this happen: <explanation>

    Instead, this happened: <explanation>

    Backtrace: (copy from terminal)
## Pull Requests

Pull requests are the primary mechanism we use to improve Tessel. GitHub itself
has some [great documentation][pull-requests] on using the Pull Request
feature.

[pull-requests]: https://help.github.com/articles/using-pull-requests/

### 1. Make the issue
The first step is to make sure there is an existing issue for bug fix or feature you are working on and that you are the person assigned to it. Check out the [Feature Requests](#feature-requests) or [Bug Reports](#bug-reports) sections above to learn more about how & when those issues are made.

### 2. Set up your branch
If you haven't already, [fork the repository](https://help.github.com/articles/fork-a-repo/) that you'll be improving and create a branch that you'll be working on. You can do this with `git checkout -b my-feature-branch` once you've pulled your fork.

### 3. Make the changes
Fix the bug or add the feature. Please make descriptive and focused git commits. Be sure to add relevant tests. If you have any questions, feel free to comment on the original Github issue and we'll get back to you as quickly as possible.

### 4. Make a Pull Request
Once you've implemented and tested the change, open a [pull request][pull-requests] on your branch. If there is someone in the community that you would specifically like to have review your code, call them out on the pull request with a comment like `review? @johnnyman727` and that person will assist shortly. Otherwise, one of the project [Collaborators](https://github.com/technicalmachine/tessel-project/blob/master/Governance/Moderating.md) will review the code and provide feedback.

### 5. Merge the PR
After the code has been reviewed, the Collaborator may suggest several things to change about the contribution before it's ready. After the necessary changes have been made, the Collaborator will accept the pull request and merge it into the master branch! 

## Issue Triage

The project Collaborators may not have time to investigate every issue. If you find an older issue that nobody has commented on, it would be very appreciated if you could reproduce the issue, make a simple test case if necessary, and potentially suggest the root cause and/or solutions.

## Landing Pull Requests

Collaborators are permitted to merge pull requests submitted to any Tessel repository.

When merging a pull request, you should modify the original commit message to include additional meta information regarding the change process:

- A `Reviewed-By: Name <email>` line for yourself and any other Collaborators who have reviewed the change.
- A `PR-URL:` line that references the full GitHub URL of the original pull request being merged so it's easy to trace a commit back to the  conversation that led up to that change.
- A `Fixes: X` line, where _X_ is either includes the full GitHub URL for an issue, and/or the hash and commit message if the commit fixes a bug in a previous commit. Multiple `Fixes:` lines may be added if appropriate.

See the commit log for examples such as
[this one](https://github.com/iojs/io.js/commit/b636ba8186) if unsure exactly how to format your commit messages.

Additionally:

- Double check PR's to make sure the person's _full name_ and email address are correct before merging.
- Except when updating dependencies, all commits should be self-contained.  Meaning, every commit should pass all tests. This makes it much easier when bisecting to find a breaking change.

### Technical HOWTO for PRs

_Optional:_ ensure that you are not in a borked `am`/`rebase` state

```text
$ git am --abort
$ git rebase --abort
```

Checkout proper target branch

```text
$ git checkout v1.x
```

Update the tree

```text
$ git fetch origin
$ git merge --ff-only origin/v1.x
```

Apply external patches

```text
$ curl https://github.com/iojs/io.js/pull/xxx.patch | git am --whitespace=fix
```

Check and re-review the changes

```text
$ git diff origin/master
```

Check number of commits and commit messages

```text
$ git log origin/master
```

If there are multiple commits that relate to the same feature or one with a feature and separate with a test for that feature - you'll need to squash them (or strictly speaking `fixup`).

```text
$ git rebase -i origin/master
```

This will open a screen like this (in the default shell editor):

```text
pick 6928fc1 crypto: add feature A
pick 8120c4c add test for feature A
pick 51759dc feature B
pick 7d6f433 test for feature B

# Rebase f9456a2..7d6f433 onto f9456a2
#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

Replace a couple of `pick`s with `fixup` to squash them into a previous commit:

```text
pick 6928fc1 crypto: add feature A
fixup 8120c4c add test for feature A
pick 51759dc feature B
fixup 7d6f433 test for feature B
```

Replace `pick` with `reword` to change the commit message:

```text
reword 6928fc1 crypto: add feature A
fixup 8120c4c add test for feature A
reword 51759dc feature B
fixup 7d6f433 test for feature B
```

Save the file and close the editor, you'll be asked to enter new commit message for that commit, and everything else should go smoothly. Note that this is a good moment to fix incorrect commit logs, ensure that they are properly formatted, and add `Reviewed-By` line.

Time to push it:

```text
$ git push origin master
```

---

Attribution: Parts of this guide are based on the io.js [Collaborator Guide](https://github.com/iojs/io.js/blob/v1.x/COLLABORATOR_GUIDE.md).
