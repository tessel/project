# <img src="https://cloud.githubusercontent.com/assets/80639/7736468/c78ac686-fef8-11e4-9931-cc3ef8fd37a0.png" width="600" alt="The Tessel Project">

[![Code of Conduct](https://img.shields.io/badge/%E2%9D%A4-code%20of%20conduct-blue.svg?style=flat)](https://github.com/tessel/project/blob/master/CONDUCT.md) [![](https://slackin.tessel.io/badge.svg)](https://slackin.tessel.io/)

## What is this project?
Tessel is a completely open source and community-driven IoT and robotics development platform. It encompasses development boards, hardware module add-ons, and the software that runs on them.

One common misconception is that we're a company. We're not! We're just a collection of (unpaid) people who find it worthwhile to spend our time building towards the Tessel Project [mission](MISSION.md).

### What's a Tessel?
Our website [tessel.io](https://tessel.io) should give you an overview of the hardware we build. You can see examples of things people have built on Tessel on our [projects page](https://tessel.io/projects).

### What is this Tessel Project all about?
Tessel is about designing intuitive and accessible hardware development experiences around the open web. Feel free to read more about our [mission](MISSION.md) and [governance model](GOVERNANCE.md). Please also read and adhere to our [code of conduct](https://github.com/tessel/project/blob/master/CONDUCT.md).

### What can I find in this repo?
This repository is for the organization and governance of the Tessel project as a whole. For code, see the [Tessel GitHub organization](https://github.com/tessel).

For an introduction to the project's organization and key repos, check out the [Technical Overview](https://tessel.gitbooks.io/t2-docs/content/Debugging/Technical_Overview.html).

# Current goals

The Tessel Project has these goals for September 2017 (our next Tessel Summit). They are organized into two overarching themes, each with several supporting tasks:

1. **Grow the community to increase contributions and encourage both inclusion and accessibility to newcomers.**
  * [ ] Build effective working groups that can complete their tasks with measurable results. Celebrate the work of each of the working groups as goals are accomplished
  * [ ] Upgrade our documentation. Build more fritzing examples, API prototypes, and call out features that are currently missing from the docs
  * [ ] Update the tessel.io website to more accurately represent the project and its plans (https://github.com/tessel/tessel.io/issues/102)
2. **Support and grow the number of production deployments of Tessel in the field.**
  * [ ] Create a guide to production-scale deployment of a Tessel project
  * [ ] Research user needs: What do people need to use T2 in production? Why aren't they using it currently?
  * [ ] Build Reach (https://github.com/tessel/project/issues/142)
  * [ ] Get to JavaScript parity with Rust API and documentation (https://github.com/tessel/tessel-rust). Figure out JS-Rust inter-exection
  * [ ] Investigate and possibly execute a Tessel hardware upgrade (Tessel 2.1) for more RAM and Flash. This should legitimize the platform and build out the capabilities so there is less user experience friction

## Working groups

The Tessel Project forms working groups to accomplish our year-long goals.

### What's a working group?
* A working group (WG) is a group of people working toward a defined, accomplishable goal.
* WGs create some output measure of progress on a regular (every 1-2 weeks) schedule, whether that's meeting notes or something else

### What working groups do we need to accomplish this year's goals?
* **[Website WG](https://github.com/tessel/tessel.io/issues/102)**:  Create a better website for what we are & what we plan to be based on this year’s goals. [Learn more/get involved](https://github.com/tessel/tessel.io/issues/102). On Tessel's Slack, join #website-wg
* **[Rust WG](https://github.com/tessel/tessel-rust)**: Get the Rust language to 1st class support on Tessel. On Tessel's Slack, join #rust-wg
* **[Reach WG](https://github.com/tessel/project/issues/142)**: ship Reach, a low-power sensor node for Tessel ecosystems. On Tessel's Slack, join #reach-wg
* **[Production WG](https://github.com/tessel/project/issues/207)**: investigate user needs for production & write a guide on how to take a Tessel project to product scale. Also build and document GPIO/GUTS (Great Uses for Tessel in Stuff e.g. hacking a production system) projects. [Learn more/get involved](https://github.com/tessel/project/issues/207). On Tessel's Slack, join #production-wg
* **Tessel Memory WG**: make larger projects deployable on T2, possibly as a 2.1 Tessel hardware

# How can I get involved with the Tessel Project?

## Quickest start

Find an issue tagged ["contribution-starter"](https://github.com/issues?q=is%3Aopen+is%3Aissue+label%3Acontribution-starter+user%3Atessel) and start working!

## Quick start

1. [Join the team slack](//tessel-slack.herokuapp.com) and express your interest in contributing in the #community channel. You will receive a warm welcome.
2. Read the [Technical Overview](https://tessel.gitbooks.io/t2-docs/content/Debugging/Technical_Overview.html) to see if any particular area of the project strikes your fancy.
3. Back on Slack, let us know if there's something in particular you'd like to work on – we're happy to help you get set up! A general post in #community should work.

## The (slightly) longer version

By contributing to Tessel, you'll be a valued member of a passionate, diverse team and one of the pioneers of the burgeoning connected devices space. Here are some ways in which you can get involved:

* [How to contribute to Tessel 2 (without needing hardware)](https://tessel.io/blog/118385488827/contributing-to-tessel-2-without-hardware)
* Submit code or patches for [Tessel modules and tools](https://github.com/tessel)
* [Discuss the Tessel Project's goals and governance](https://github.com/tessel/project/issues)

Learn more about how we [collaborate using Github](CONTRIBUTING.md):

* [Feature Requests](CONTRIBUTING.md#feature-requests)
* [Bug Reports](CONTRIBUTING.md#bug-reports)
* [Pull Requests](CONTRIBUTING.md#pull-requests)
* [Issue Triage](CONTRIBUTING.md#issue-triage)

If you have questions, please make a post on [our forums](https://forums.tessel.io) and someone from the community will respond shortly. All contributors are expected to follow our [Code of Conduct](CONDUCT.md).

# Reach out

Get involved with our community in any way you are interested:

* **[Join us on Slack](https://tessel-slack.herokuapp.com/) &mdash; Collaboration and real time discussions (Recommended! - ask your questions here).**
* [Tessel Forums](https://forums.tessel.io/) &mdash; General discussion and support by the Tessel community.
* [tessel.hackster.io](http://tessel.hackster.io) &mdash; Community-submitted projects made with Tessel.
* [tessel.io/community](http://tessel.io/community) &mdash; Join a Tessel meetup near you! Meetups happen around the world and are the easiest way to play with hardware in person.
* [#tessel on Freenode](https://www.irccloud.com/#!/chat.freenode.net:6667/%23tessel) &mdash; IRC channel for development questions and live help.
* [Stack Overflow](http://stackoverflow.com/questions/tagged/tessel) &mdash; Technical questions about using Tessel.

# Read more

* [Contribution Guide](CONTRIBUTING.md)
* [Mission](MISSION.md) of the Tessel Project
* [Code of Conduct](CONDUCT.md) for the Tessel community
* [Governance Structure](GOVERNANCE.md) and [Membership](TEAM.md) of the Steering Committee
* [Meeting Notes](meetings/)

# Contribute

Tessel is in part funded by contributions through [Open Collective](https://opencollective.com/tessel).

## Backers

Support us with a monthly donation and help us continue our activities. [[Become a backer](https://opencollective.com/tessel#backer)]

<a href="https://opencollective.com/tessel/backer/0/website" target="_blank"><img src="https://opencollective.com/tessel/backer/0/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/1/website" target="_blank"><img src="https://opencollective.com/tessel/backer/1/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/2/website" target="_blank"><img src="https://opencollective.com/tessel/backer/2/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/3/website" target="_blank"><img src="https://opencollective.com/tessel/backer/3/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/4/website" target="_blank"><img src="https://opencollective.com/tessel/backer/4/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/5/website" target="_blank"><img src="https://opencollective.com/tessel/backer/5/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/6/website" target="_blank"><img src="https://opencollective.com/tessel/backer/6/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/7/website" target="_blank"><img src="https://opencollective.com/tessel/backer/7/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/8/website" target="_blank"><img src="https://opencollective.com/tessel/backer/8/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/9/website" target="_blank"><img src="https://opencollective.com/tessel/backer/9/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/10/website" target="_blank"><img src="https://opencollective.com/tessel/backer/10/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/11/website" target="_blank"><img src="https://opencollective.com/tessel/backer/11/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/12/website" target="_blank"><img src="https://opencollective.com/tessel/backer/12/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/13/website" target="_blank"><img src="https://opencollective.com/tessel/backer/13/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/14/website" target="_blank"><img src="https://opencollective.com/tessel/backer/14/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/15/website" target="_blank"><img src="https://opencollective.com/tessel/backer/15/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/16/website" target="_blank"><img src="https://opencollective.com/tessel/backer/16/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/17/website" target="_blank"><img src="https://opencollective.com/tessel/backer/17/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/18/website" target="_blank"><img src="https://opencollective.com/tessel/backer/18/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/19/website" target="_blank"><img src="https://opencollective.com/tessel/backer/19/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/20/website" target="_blank"><img src="https://opencollective.com/tessel/backer/20/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/21/website" target="_blank"><img src="https://opencollective.com/tessel/backer/21/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/22/website" target="_blank"><img src="https://opencollective.com/tessel/backer/22/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/23/website" target="_blank"><img src="https://opencollective.com/tessel/backer/23/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/24/website" target="_blank"><img src="https://opencollective.com/tessel/backer/24/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/25/website" target="_blank"><img src="https://opencollective.com/tessel/backer/25/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/26/website" target="_blank"><img src="https://opencollective.com/tessel/backer/26/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/27/website" target="_blank"><img src="https://opencollective.com/tessel/backer/27/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/28/website" target="_blank"><img src="https://opencollective.com/tessel/backer/28/avatar.svg"></a>
<a href="https://opencollective.com/tessel/backer/29/website" target="_blank"><img src="https://opencollective.com/tessel/backer/29/avatar.svg"></a>

## Sponsors

Become a sponsor and get your logo on our README on Github with a link to your site. [[Become a sponsor](https://opencollective.com/tessel#sponsor)]

<a href="https://opencollective.com/tessel/sponsor/0/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/1/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/2/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/3/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/4/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/5/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/6/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/7/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/8/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/9/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/9/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/10/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/10/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/11/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/11/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/12/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/12/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/13/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/13/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/14/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/14/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/15/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/15/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/16/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/16/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/17/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/17/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/18/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/18/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/19/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/19/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/20/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/20/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/21/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/21/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/22/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/22/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/23/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/23/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/24/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/24/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/25/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/25/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/26/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/26/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/27/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/27/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/28/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/28/avatar.svg"></a>
<a href="https://opencollective.com/tessel/sponsor/29/website" target="_blank"><img src="https://opencollective.com/tessel/sponsor/29/avatar.svg"></a>
