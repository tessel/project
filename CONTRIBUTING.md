# Contributing

This guide is for anyone interested in contributing to Tessel.

## I want to contribute! What do I do?
1. **If you haven't already, get started with your Tessel 2!** Go to the [Tessel 2 start page](http://tessel.github.io/t2-start/) and try it out! This should get you set up with using the CLI, connecting to Wifi, and using modules. Take note of anything confusing or not-working and make issues for them on [Tessel 2 Start's issue tracker](https://github.com/tessel/t2-start/issues). These make great first contributions!

1. **Get to know the team.** Our primary communication channel is [Slack](https://tessel-slack.herokuapp.com/). We recommend downloading the app and keeping it open while you're working on Tessel; it's very useful for asking quick questions. Important channels:

  * #engineering for most of your technical questions
  * #reviews to ask for a code review
  * #events-speaking if you're interested in giving conference talks

1. **Get to know T2's tech stack and repos.** You'll be much more equipped to make meaningful contributions if you read the [Tessel 2 Technical Overview](https://tessel.gitbooks.io/t2-docs/content/debugging/Technical_Overview.html). This guide goes over the main repositories, where you can find relevant code and design files, and how the Tessel 2 system architecture works.

1. **Find a mentor.** On Tessel's slack, make a post in the #community channel and ask for help finding something to work on. Alternately, reach out to any [Team Member](https://github.com/tessel/project/blob/master/TEAM.md) via email and ask them if they will help you get started contributing to the Tessel Project.

1. **Get to know your mentor.** Once you're part of the team and you have a high-level understanding of how Tessel 2 works, get in touch with the person that introduced you to the project and set up a time to chat. This informal call will help you understand the current state of the project, where your help is needed most, and how you can get started.

1. **Do something!** Your mentor can help you find something to work on, or look for the label `contribution-starter` on any Tessel repo. Pick something, ask questions, and get started! You don't have to completely solve an issue in order to contribute– post anything you learn on the issue in order to help other contributors.

---
# Contribution Guidelines

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
