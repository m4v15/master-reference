Inspired by [dwyl's contribution workflow](https://www.github.com/dwyl/contributing).

# Contribution guidelines
+ [Before starting work](#before-starting-work)
+ [Starting work](#starting-work)
  + [Commits](#commits)
  + [Pull requests](pull-requests)
+ [Instructions for maintainers](#instructions-for-maintainers)

## Before starting work
1. Search this repo's [issues](https://www.github.com/lotus-coding-school/master-reference/issues) to see if an issue exists for the problem you are solving.
2. If the issue does not exist, create it. Include a descriptive body.
3. If your new issue relates to any others, reference those issues in the body. This enables others to follow the history of the topic.
4. Assign [the appropriate label](#labels).
5. Indicate on the issue that you would like to take it on. Assign one of the reviewers above if you need a response.
6. Once you are sure of what you need to do and that it is needed, assign yourself to the issue.
7. Clone, and create a new branch for your work

### Labels
`week-<name-here>` - if your new issue relates to a specific week of the course (e.g. `week-toolkit`)
`bug` - something in this repo is broken (e.g. a link)
`discuss` - you'd like the community's input before you start any work
`question` - you're not actually sure whether this is an issue or not and would like confirmation
`help wanted` - you would like some help in completing work on this issue

## Starting work

### Commits
The commit history of each file should tell a story
+ [Describe your changes well](https://gist.github.com/mikepea/863f63d6e37281e329f8#describe-your-changes-well-in-each-commit)
+ [Commits should be granular](https://gist.github.com/mikepea/863f63d6e37281e329f8#keep-it-small)
+ **It is important that you reference an issue in each commit** - use [multiline messages](#multiline-messages)

#### Multiline messages
You will want to space your commit messages over more than one line. Commit without the `-m` to bring up a text editor in which to write the commit message.

You may want to configure git to use your preferred text editor, if you do not like the default. ie. [Set atom to be default commit message editor](https://help.github.com/articles/associating-text-editors-with-git/#using-atom-as-your-editor).

The message should have the following format:
```md
short description under 50 chars.
[newline]
more detailed description (may be bullet points)
[newline]
related #[issue number]
```
or
```md
short description under 50 chars.
[newline]
related #[issue number]
```

### Pull Requests
Once you have finished your work, push up your branch and make a pull request. Remember, a pull request should be as small as possible. This makes the review process quick and easy.

Make sure your PR has the following
1. [A descriptive title](https://gist.github.com/mikepea/863f63d6e37281e329f8#ensure-there-is-a-solid-title-and-summary) - distinct from others and therefore searchable
2. [A body with details of everything in the pull.](https://gist.github.com/mikepea/863f63d6e37281e329f8#ensure-there-is-a-solid-title-and-summary)
3. Reference to any/all related issues in description.
4. Assignees - add all the [maintainers of `master-reference`](https://github.com/foundersandcoders/master-reference/blob/master/ROLES.md) to every PR:
   + [@shiryz](https://github.com/shiryz)
   + [@MynahMarie](https://github.com/MynahMarie)
5. Reviewers
   + add anyone other than the maintainers, who you think should be aware of you contents of your PR
    e.g. anyone else who has collaborated with you on this issue / anyone mentioned in the file you are uploading / mentors delivering this material in another campus
   + if your PR _requires_ a review from a particular person / people _before_ it is ready to be merged, specify this within the body of your PR

## Instructions for maintainers
Once a pull request has been approved by two maintainers it can be merged. In time critical situations, one approval may suffice, as long a the pull request is small and is not suggesting any major change.

# Thank you!
P.S. please star this repo.
