# Contributing to this repository
As a member contributor, here are the guidelines that you should follow.

Use this repository to contribute to this project as easy and transpartent as possible, whether it's:
* Reporting a bug
* Discussing the current state of the Technical Specifications
* Submitting a fix
* Proposing new features
* other

## We Develop Technical Specifications for this Project with GitHub
* We use this GitHub repository to host the Technical Specifications related to this project (only), to track issues and feature requests, 
as well as accept all pull requests related to this project.
* All changes happen through Pull Requests `PR's`
* We use [GitHub Flow](https://github.com/OpenManufacturingPlatform/rules_of_engagement) as described in the OMP [rules of engagement](https://github.com/OpenManufacturingPlatform/rules_of_engagement)

### Branches
* Please do not apply direct pull requests against these branches:
   * `master` 
      * This branch contains documents agreed by the Working Group (WG) and ratified by the Steering Committee (SC).
   * `development`
      * It is used by the WG Chair to merge agreed content from `feature-branches` or to derive new `feature-branches`.
* The technical work will be developed in `feature-branches`, which are derived by the WG Chair from the `development` branch with the intention of developing a particular feature, section or topic.
   * Once the content of these feature branches are completed and agreed by the WG, its content will be merged by the WG Chair into the `development` branch. The pull request used for these merges should be prefix with the name [ADMIN], e.g. `[ADMIN] merge feature-branch-x into development branch`

### Issues
1. We use `Issues` for tracking all type work in the repository: `development`, `new features`, `bug fixes`, `discussions`, `Review & Approval`, etc.

2. Create an `Issue`

Issue Types        |   Description
-------------------| ------------------------------------------------------
`Bug Report`         | This `Issue` is dedicated to report a problem in a document.
`Feature Request`    | This `Issue` is used when the contributor wants to discuss the introducion of a new feature.
`Custom`             | When your new issue doesn't fit in any of the above classification, then you can create an `Issue` different from the above template.

Issue has to be created one day before the Working Group meeting.

3. The Chair will further assign a `label` to your `Issue` according to this table:
   * `labels` are assigned to `PR's` and `Issues` as a way to classify the work

Label Types        | Description
-------------------| ----------------------------------------
`editorial`        | The changes in the `PR` are only editorial changes.
`bug`              | This label indicates that the item is related to a bug found in the Technical Specifications.
`enhancement`      | This label indicates that the item contains changes to an existing feature.
`new feature`      | The item contains branch new features.
`review & approval`| The `PR` is put forward for approval, comments will be accepted during a specific period of time. If no objections have been received in that period then, the `PR` is approved and it can be merged.
`request for information`| The WG is requesting further information. If a period of time not information is received, then the `PR` can be closed.
`New label`             | When none of the above labels are suitable.

### Pull Requests
1. Start editing a document in the assigned `feature-branch`
   * If a `PR` is created against the incorrect `feature-branch` it will be `Closed`.
   * Each `PR` SHOULD be linked to an `Issue`.
   * Each `PR` SHOULD contain changes related to one technical document only. If the changes cover more than one document, then create one `PR` per each document
   * Commit changes often. Each time that you save a change GitHub creates a new `commit`. A `PR` may contain one or more `commits`.
   * `PR` has to be created one working day before the Working Group meeting.

### 3. Pull Request Discussion
1. Members can provide comments to any `PR` or `Issue` via:
a. Offline comments
b. During conference calls or face to face meetings
c. `review & approval` period:
   * Upon a WG or Chair agreement, the discussion and approval of a `PR` can be deferred  to an offline discussion. 
   * In this case, the `PR` will be labelled as `review & approval`. 
   * During a prefixed period of time, members can submit comments and/or objections to the `PR`. 
   * If at the end of the review period not objections have been received, then the `PR` can be `merged`.
   * The review period is fixed by the group an SHOULD be measured in days: Three working days after the presentation of the pull request in the working group meeting.

> Note: If a `PR` or `Issue` is labelled as `request for information` and not input is received after a prefixed period of time, then the `PR` or `Issue` MAY be closed.

### Pull Request Decision
1. The final classification of a `PR` is agreed by the Working Group: [Consensus Decision-Making]():
  * **`Closed`:** The `PR` was reviewed by the WG but it was decided to close it without merging it.
  * **`Merged`:** The WG agreed to `merge` the `PR`.

### OMP Resources:
* Code of Conduct (TBD)
* Roles and Access Rights (TBD)
* [Document Templates](https://github.com/OpenManufacturingPlatform/templates)
### GitHub Resources
* [For a Repo](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)
* [Issue Creation](https://help.github.com/en/github/managing-your-work-on-github/creating-an-issue)
* [PR Creation](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)


