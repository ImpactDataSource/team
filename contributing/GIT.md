GIT
==

All code developed for our projects must be tracked in version control through
GIT. With the exception of generic components that we choose to
[open source](./OPEN_SOURCE.md), all repositories will be set to private in our
GitHub account. Even so, care should be taken against committing any credentials
or potentially sensitive information.

#### Branching

Projects follow the GIT Flow branching model, with development being performed
on named branches. When a feature is complete, a pull request is opened in
GitHub for review by another member of the team. Traditional GIT Flow allows for
`feature`, `bug`, and `chore` branches. Below is a summary of each type of
branch and its purpose:

* **master** Should always represent what is currently deployed to production.
Never work directly on master

* **develop** Represents the current working branch. Should be mostly stable but
is ok to break. This should automatically deploy to the demo environment where
most QA will take place.

* **feature/*** Feature branch. These branches should always branch off of and
merge back on to `develop`. Format should be
feature/brief_functionality_description_121984369 where number represents
Pivotal story id.

* **bug/*** Bug branch. Same as feature where it always branches off of develop
but branch name is prefaced with "bug/...".

* **hotfix/*** Hotfix branch. Like a bug, but the functionality is more urgent
and needs to be released before the next release cycle. Always branches off of
`master` and is merged into `master` and `develop` when completed. Is usually
accompanied by a mid-cycle production release.

Once the feature is complete and marked as Ready to Merge, all commits can be
squashed, if desired, into a single commit following our
[Commit Message Format guidelines](#commit-message-format). The
approved pull request will be merged as a fast-forward commit.

For this reason it is important that work on a feature or bug branch represent a
narrow vertical slice of complete functionality. Refactoring neighboring code or
fixing bugs should happen on their own branch unless they are directly required
for the feature work being performed.

#### Commit message format

Also look into Google's Commit Message Guidelines as they provide a great
example of writing which are easier to follow when looking through a project
history.

The header of a commit message should incude the Pivotal Tracker story id along
with a brief description of the work completed.

ex. `[#121984369] update logo upload functionality on account page`

If greater detail is required, you can use bullited lists in the body section of
a commit message.

When constructing your commit message:
* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot (.) at the end

Work in progress development happening on feature branches do not need to adhere
to this commit message format until a pull request is opened and marked as
ready for merge. While a feature is in progress it is encouraged to commit often
with descriptive messages.

All commits representing a vertical slice of usable functionality can be
squashed upon approval prior to merge.
