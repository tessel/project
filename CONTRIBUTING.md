# Contributing

This guide is for anyone interested in contributing to Tessel.

## Feature Requests
To request a change in any components of the Tessel ecosystem such as adding a command line interface option, adding support for various drivers in the kernel, or suggesting a new piece of hardware, please create an RFC. Detailed instructions can be found on [the RFC repo](https://github.com/tessel/rfcs).

## Bug Reports
Every once in a while, you may run into a bug when using Tessel. Please do report it! If you aren't sure where to report it (system overview coming soon!), please ask on the [Forums](http://forums.tessel.io) or just open an issue on this github repo (a Team Member will move the issue if necessary). It's much preferred to report an issue that may already exist rather than risk leaving the flaw unexposed.

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
Once you've implemented and tested the change, open a [pull request][pull-requests] on your branch.

If there is someone in the community that you would specifically like to have review your code, call them out on the pull request with a comment like `review? @johnnyman727` and that person will assist shortly.

Otherwise, one of the project [Team Members](https://github.com/tessel/project/blob/master/TEAM-MEMBERS.md) will review the code and provide feedback.

You may also wish to post to the #reviews channel on [Tessel Slack](https://tessel-slack.herokuapp.com/).

### 5. Merge the PR
After the code has been reviewed, the Team Member may suggest several things to change about the contribution before it's ready. After the necessary changes have been made, the Team Member will accept the pull request and merge it into the master branch!

## Issue Triage

The project Team Members may not have time to investigate every issue. If you find an older issue that nobody has commented on, it would be very appreciated if you could reproduce the issue, make a simple test case if necessary, and potentially suggest the root cause and/or solutions.

## Landing Pull Requests

Team Members are permitted to merge pull requests submitted to any Tessel repository.

When merging a pull request, you should modify the original commit message to include additional meta information regarding the change process:

- A `Reviewed-By: Name <email>` line for yourself and any other Team Members who have reviewed the change.
- A `PR-URL:` line that references the full GitHub URL of the original pull request being merged so it's easy to trace a commit back to the  conversation that led up to that change.
- A `Fixes: X` line, where _X_ is either includes the full GitHub URL for an issue, and/or the hash and commit message if the commit fixes a bug in a previous commit. Multiple `Fixes:` lines may be added if appropriate.

See the commit log for examples such as
[this one](https://github.com/iojs/io.js/commit/b636ba8186) if unsure exactly how to format your commit messages.

Additionally:

- Double check PR's to make sure the person's _full name_ and email address are correct before merging.
- Except when updating dependencies, all commits should be self-contained.  Meaning, every commit should pass all tests. This makes it much easier when bisecting to find a breaking change.

---

Attribution: Parts of this guide are based on the io.js [COLLABORATOR_GUIDE](https://github.com/nodejs/io.js/blob/master/COLLABORATOR_GUIDE.md).
