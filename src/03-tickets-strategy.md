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
**Actual result:** the system behavior as is. Also images, videos, log output and any other additional information should be attached.
