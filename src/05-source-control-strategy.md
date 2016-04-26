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
