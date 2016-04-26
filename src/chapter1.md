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
