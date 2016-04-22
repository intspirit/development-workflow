# development-workflow
Different development strategies that may help

## The team
1. Project manager
2. Team lead, developer (TL)
3. Developer(s)
4. Tester

## Pipeline strategy
*Brief overview of the task life cycle:*
 - new task is created;
 - analyzing the task; (pre-development)
 - development;
 - tech review;
 - testing;
 - deploy;
 - task is finished.

*Details in terms of bug tracker:*

We need to create the following lists in our Trello board:
- **Icebox** (this list is used to keep tasks that will not be implemented soon, in the nearest releases, just to not miss anything)

- **Backlog**
	> Any person can create the task/bug here and assign it to PM. After that PM analyze the task/bug, contact with a person who has created task, add details, description, screenshots and so on. After that PM move task to “Ready to develop” and assign to the one of developers.
- **Ready to develop**
	> Fully described tasks/bugs are kept in this list. Developer takes one of his tasks in accordance to priority and move it to “Development”.
- **Development**
	> Developer is working with the task. So this list contains tasks are under development in the current time. After the task is finished developer move it “Ready for tech review” and assign to TL.
- **Ready for tech review**
 	> Here we keep tasks/bugs are waiting for tech review. All of them assigned to TL. TL moves task/bug to “Tech review”
- **Tech review**
	> Team lead reviews the task. There are two possible results:
  - Fail review :-1: - TL moves task/bug to “Ready to develop” and assign back to developer with some comments about what is need to be fixed.
  - Pass review :+1: - TL moves task/bug to “Ready for testing”
- **Ready for testing**
	> The tasks/bugs waiting for testing (assigned to tester) are kept here. Tester moves task/bug to “Testing”
- **Testing**
	> Tester tests task/bug manually and/or write automated tests. There are two possible scenarios:
	- Tests fail :exclamation: - tester move task/bug to “Ready to develop” with comments and assign back to the developer.
	- Tests pass :+1: - tester move task/bug to “Ready to release” and assign to TL.
- **Ready to release**
	> TL merges code to branch ‘develop’ and close the task/bug. Moves to “Closed”.
- **Closed** (Implemented tasks / fixed bugs here).

## Tickets strategy
*General task or bug forkflow:*
- Developer takes task/bug to work on.
- Developer creates a new branch with name ‘task/some-title-<N>’ or ‘bug/some-title-<N>’, where <N> is number of issue in Trello.
- Developer works on task/bug in created branch.
- After work is done developer creates pull request from his branch to develop branch.
- Team lead verifies code and add comments (if needed).
- Developer fixes issues in the code (if needed).
- TL merges branch to develop.

*Standard bug description*

**Steps to reproduce:**
1. Log in to system as user/password using given URL
2. Open page ‘our_cool_page’ (via direct URL or UI element)
3. `Open tab ‘my_tab’` / `go this submenu` / `something else understandable`
4. `Add / change something`

**Expected result:** `some result we expect`

**Actual result:** the current system behavior

Also images, videos and any other additional information should be attached.

## Deploy strategy
We need to have at least 3 branches and 3 domains accordingly:
- **production** (or master) - manually pushed to - lawcus.com
- **develop** - automatically pushed to - dev.lawcus.com or develop.lawcus.com or something like this
- **release** - automatically pushed to - release.lawcus.com (this branch and subdomain should apear only during release)

*Also it would be great to automatically create/delete subdomain for each new created branch like task-some-title-32.lawcus.com so we can test the particular feature/bug fix. But it can be not realistic due to server limitations on subdomains or some technical issues, I’m not sure.*

## Source control strategy
As was described in previous point we need the exact dependencies for master (production) and develop branches:
- branch master (production) -> production domain -> live URL
- branch develop -> development domain -> dev URL

Also we need temporary branch
- release -> release domain -> release URL

the release branch and domain are needed only for testing recently implemented features or bug fixes (included to the current release/milestone), TL pushes the code from develop branch to release but take the database from a live site (production) so we can do testing on real data.

*There are some important points about the release:*

> 1. No new task!
2. Create new branch for every fix -> after fix is added, reviewed and tested merge to release branch.
3. After all testing and fixing are done -> push code from branch release to develop and master branches.
4. Remove release branch and domain.

*Also we can meet such thing like `bug in production`. The goal is to avoid such situations but it happens sometimes. The algorithm is the following:*

> 1. Create new branch.
2. Use basic forkflow as for usual bug.
3. After fix TL merges branch to master, than to develop or release (if we are on release right now)

## Scrum strategy
The preferred way is video/voice conference. But the short summary should be pushed to #scrum channel in Slack.
The example is

**Yesterday:**
1. Task #N1, Task title, URL in Trello
2. Tech review of Task #N2, Task title, URL in Trello (activity type for TL only)
3. ...

**Today:**
1. Task #N1, Task title, URL in Trello
2. Tech review of Task #N2, Task title, URL in Trello (activity type for TL only)
3. ...

**Progress:** #N1 (35%), #N2 (20%), …

**Questions:**
1. question 1 about some thing (link the user for who this question is)

_**Availability**: 10am - 9pm with random brakes / 10am - 1pm, then 4pm - 10pm or something like this (the SAME TIMEZONE should be used)_

## Work strategy
All times are used in Moscow TIMEZONE. For scrum the PST is added in brackets.

> - 9:00am - start
- 9:00am - 9:30am - each team member review the tasks/bugs/everything and prepare to scrum
- 9:30am (11:30pm) - 10:00am (12:00am) - scrum
- 10:00am - 11:00am - discussing questions, change plan for the day if needed and so on
- 11:00am - 6:00pm (end of the day) - working on tasks

The main idea is to do all preparing, reviewing, discussing work and scrum during the first 2 hours in the beginning of the day (it can be less than two hours actually). So the rest of the day is going to be very efficient. Each team member understands fully what is his goal for the day.
