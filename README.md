# The Tessel Project

### What is this project?
Tessel is a completely open source and community-driven IoT and robotics development platform. It encompases development boards, hardware module add-ons, and the software that runs on them. Tessel is about designing intuitive and accessible hardware development experiences around the open web. Feel free to read more about our [mission](/Governance/Mission.md) and [governance model](/Governance/Governance.md).
### How can I get involved?
By contributing to Tessel, you'll be a valued member of a passionate, diverse team and one of the pioneers of the burgeoning connected devices space. 

There are a handful of different ways to get involved in the project:

* [Feature Requests](#feature-requests)
* [Bug Reports](#bug-reports)
* [Pull Requests](#pull-requests)
* [Issue Triage](#issue-triage)

If you have questions, please make a post on [our forums](forums.tessel.io) and someone from the community will respond shortly.

All contributors are expected to follow our [Code of Conduct](Conduct.md).

## Feature Requests
To request a change in any components of the Tessel ecosystem such as adding a command line interface option, adding support for various drivers in the kernel, or suggesting a new pece of hardware, please create a new post on the [Forums with the `contributing` tag](https://forums.tessel.io/c/contributing). We have no specific format for the RFC but feel free to check out [this example](https://forums.tessel.io/t/wifi-api-from-js-for-the-cc3000/399). The community will then discuss the change and if a moderator approves of the RFC, they will create an issue on the appropriate repository. If you agree to it, you may be assigned to the issue and expected to develop that feature.

## Bug Reports
Every once in a while, you may run into a bug when using Tessel. Please do report it! If you aren't sure where to report it (system overview coming soon!), please ask on the [Forums](forums.tessel.io) or just open an issue on this github repo (a moderator will move the issue if necessary). It's much preferred to report an issue that may already exist rather than risk leaving the flaw unexposed.

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
Once you've implemented and tested the change, open a [pull request][pull-requests] on your branch. If there is someone in the community that you would specifically like to have review your code, call them out on the pull request with a comment like `review? @johnnyman727` and that person will assist shortly. Otherwise, one of the project [moderators](https://github.com/technicalmachine/tessel-project/blob/master/Governance/Moderating.md) will review the code and provide feedback.

### 5. Merge the PR
After the code has been reviewed, the moderator may suggest several things to change about the contribution before it's ready. After the necessary changes have been made, the moderator will accept the pull request and merge it into the master branch! 

## Issue Triage

The project moderators may not have time to investigate every issue. If you find an older issue that nobody has commented on, it would be very appreciated if you could reproduce the issue, make a simple test case if necessary, and potentially suggest the root cause and/or solutions.



