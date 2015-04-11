# Moderator Guide

This guide is intended to help Moderators for the Tessel Project understand and fulfill their role: maintaining code, documentation, and triaging issues. For a definition of Moderators and information on how to become a Moderator, see the [GOVERNANCE](GOVERNANCE.md) document.

**Contents**

* [Issues and Pull Requests](#issues-and-pull-requests)
* [Accepting Modifications](#accepting-modifications)
 - [Involving the SC](#involving-the-sc)

Moderators should be familiar with the guidelines for new contributors in [the README](README.md) and also understand the project governance model as outlined in
[GOVERNANCE](GOVERNANCE.md).

## Issues and Pull Requests

Courtesy should always be shown to individuals submitting issues and pull requests to the Tessel project.

Moderators should feel free to take full responsibility for managing issues and pull requests they feel qualified to handle, as long as this is done while being mindful of these guidelines, the opinions of other Moderators and guidance of the SC.

Moderators may **close** any issue or pull request they believe is not relevant for the future of the Tessel project. Where this is unclear, the issue should be left open for several days to allow for
additional discussion. Where this does not yield input from Moderators or additional evidence that the issue has relevance, the issue may be closed. Remember that issues can always be re-opened if necessary.

## Accepting Modifications

All modifications to code and documentation should be performed via GitHub pull requests, including modifications by Moderators and SC members.

All design decisions and hardware modifications should be discussed on the [Tessel Forums](//tessel.io/forums) before a pull request is made.

All pull requests must be reviewed and accepted by a Moderator with sufficient expertise who is able to take full responsibility for the change. In the case of pull requests proposed by an existing Moderator, an additional Moderator is required for sign-off.

In some cases, it may be necessary to summon a qualified Moderator to a pull request for review by @-mention.

If you are unsure about the modification and are not prepared to take full responsibility for the change, defer to another Moderator.

Before landing pull requests, sufficient time should be left for input from other Moderators. Leave at least 48 hours during the week and
72 hours over weekends to account for international time differences
and work schedules. Trivial changes (e.g. those which fix minor bugs or improve performance without affecting API or causing other
wide-reaching impact) may be landed after a shorter delay.

Where there is no disagreement amongst Moderators, a pull request may be landed given appropriate review. Where there is discussion amongst Moderators, consensus should be sought if possible. A lack of consensus may indicate the need to elevate discussion to the
SC for resolution (see below).

All bug fixes require a test case which demonstrates the defect. The test should *fail* before the change, and *pass* after the change.

### Involving the SC

Moderators may opt to elevate pull requests or issues to the SC for discussion by assigning the ***sc-agenda*** tag. This should be done where a pull request:

- has a significant impact on the codebase,
- is inherently controversial; or
- has failed to reach consensus amongst the Moderators who are actively participating in the discussion.

The SC should serve as the final arbiter where required.

---

Attribution: Parts of this guide are based on the io.js [Collaborator Guide](https://github.com/iojs/io.js/blob/v1.x/COLLABORATOR_GUIDE.md).
