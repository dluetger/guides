---
title: Code review
permalink: /engineering/our-approach/code-review/
sidenav: true
sticky_sidenav: true
tags: engineering
layout: layouts/page
subnav:
  - text: Why reviews?
    href: "#why-reviews"
  - text: Discuss code review with your team
    href: "#discuss-code-review-with-your-team"
  - text: Tips for a successful review
    href: "#tips-for-a-successful-review"
  - text: Submitting code
    href: "#submitting-code"
  - text: Reviewing code
    href: "#reviewing-code"
eleventyNavigation: 
  parent: engineering_approach
  key: Code review
  order: 3
  title: Code review
---

_A friendly guide for reviewing code — and not each other — at TTS._

## Why reviews?
Code reviews are an incredibly important part of the development process. Our goals when reviewing code are to:

- Expose bugs before they make it to production
- Ensure consistent code quality
- Create an environment for sharing knowledge and developing skills
- Cross-pollinate debugging skills when problems arise
- Cultivate the ability to critique one’s code more strongly
- Encourage open communication between the entire team

## Discuss code review with your team
Every individual and team has a different set of expectations around code review. Discussing these expectations explicitly is the best way to make sure that everyone is on the same page.

Document and/or automate the outcomes of your discussion. A common practice is to include this information in a `CONTRIBUTING.md` file in your project's repository.

Some guiding questions for your team's code review discussion:

- What does the current code review process, at a high level, look like? Start with the feature request and discuss each step until a feature is considered "done."
- Do contributors use forks or branches?
- What's the git workflow? E.g. is main always deployable? Rebase or merge?
- Are pull requests assigned? If so what process is used?
- How many people are expected to review each pull request?
- If a patch is worked on in a pairing session, how does it get merged?
- Does your team make use of any tools to aid in code reviews? (eg: CI, Static Analysis, linters, [Conventional Comments syntax](https://conventionalcomments.org/))
- Are there any automated tools that you are not using that you would like to try?
- If commit messages aren't up to par, should they be modified before the PR is?
- What do you look for when conducting a code review?
- Should code be pulled down and tested/what QA strategy is used? merged?
- How do you know that a pull request is ready to be merged?
- Who merges code, the author or the reviewer?
- Are there any exceptions to the above process? Typos? Hotfixes?
- What about the current process do you like?
- What about the current process do you think can be improved?
- How do changes and refinements to this process get made? Retro? PR to a contributing file?

## Tips for a successful review
For a code review to be successful, we all need to be on the same page. To help
accomplish this, everyone should consider these tips.

### For everyone
- Remember that we're reviewing the code, not the author. Nothing should be given or taken personally.
- There is often more than one way to approach a solution. Discuss tradeoffs and reach a resolution quickly.
- Ask questions rather than make statements. ("What do you think about...?")
- Ask for clarification if the code or comments are unclear. ("I didn't understand. Can you please clarify?")
- Avoid selective ownership of code. ("mine", "not mine", "yours")
- Avoid using terms that could be seen as referring to personal traits.
- Be explicit, people don't always understand your intentions online.
- Be humble. ("I'm not sure — let's look it up.")
- Don't use hyperbole. ("always", "never", "endlessly", "nothing")
- Don't use sarcasm.
- Keep it real. If emoji, animated gifs, or humor aren't you, don't force them. If they are, use them with aplomb.
- Talk offline if there is too much back and forth. Post a follow-up comment summarizing the discussion.
- Praise team members when they create exemplary work or suggestions.
- Code reviews require intense concentration, don't forget to factor this in with level of effort estimates.
- Maintaining a well-organized code base requires strict discipline from all team members and will take time and effort to establish; be patient!

### For code submitters
- Link to the code review from the originating task/issue, if applicable.
- Remember that the code isn't you, don't get defensive when a reviewer is critical of the code; instead, look at it as a learning opportunity.
- Seek to understand the reviewer's perspective.
- Try to respond to every comment.
- Be grateful for the reviewer's suggestions. ("Good catch, fixing in a4994ec")
- Explain why the code exists. ("We need to work around these existing patterns")
- Extract out-of-scope changes and refactorings into future tasks/issues.
- Push commits based on earlier rounds of feedback as isolated commits to the branch. Do not squash until the branch is ready to merge. Reviewers should be able to read individual updates based on their earlier feedback.

### For code reviewers
- Understand why the code is necessary (bug, user experience, refactoring)
- Seek to understand the author's perspective.
- Clearly communicate which ideas you feel strongly about and those you don't.
- Identify ways to simplify the code while still solving the problem.
- Offer alternative implementations, but assume the author already considered them. ("What do you think about such-and-such here?")
- Sign off on the pull request with a :thumbsup: or "Ready to merge" comment.
- Wait to merge the branch until it has passed Continuous Integration testing.
- Consider using a syntax like [Conventional Comments](https://conventionalcomments.org/) in order to clarify whether a comment is blocking or non-blocking for merging the PR.

### Who merges
There's lively debate over whether the code author or reviewer should merge the pull request. Follow the idioms that your team has set; if none are present, discuss until you have a consensus. Write that down to resolve the issue quickly in the future.

### Opening a PR
[Pull Requests initiate discussion about your commits.](https://guides.github.com/introduction/flow/) We want to receive feedback quickly and make our team members aware of our proposed solutions early, so it's encouraged to open a Draft Pull Request for your new feature/bugfix soon after your first commit. The more information you provide to reviewers in the description, the more context they will have. This leads to faster reviews, and less back and forth between everyone. We strongly recommend that in-progress work is pushed up at least once a day.

CFPB has published a nice [PR Template](https://github.com/cfpb/development/blob/main/.github/PULL_REQUEST_TEMPLATE.md) which might make this easier.

## Submitting code
Before seeking a review, you should be able to check off each of the following:

- Changes are limited to a single goal (no scope creep)
- Code can be automatically merged (no conflicts)
- Code follows the standards laid out in this playbook
- Passes all existing automated tests
- New functions include new tests
- New functions are documented (with a description, list of inputs, and expected output)
- Placeholder code is flagged
- Visually tested in supported browsers and devices
- Project documentation has been updated (including the "Unreleased" section of the CHANGELOG)

## Reviewing code
When reviewing code, you should be able to check off each of the following:

- Do the changes address the project's needs?
- Do the changes respect the project's existing style?
- Does the new code avoid reproducing existing functionality?
- Are functions/classes as simple as possible?
- Is the code reasonably efficient?
- Is the usage of each function/class clear?
- Have edge cases been considered and tested for?
- Does the code represent a logical unit of work?
- Are there any glaring syntax errors that were missed?
- Are language constructs being utilized properly?
- Are any frameworks/libraries being used leveraged properly?
- Are there useful comments/documentation where needed?
