## Deploy strategy
We need to have at least 3 branches and 3 domains accordingly:
- **production** (or master) - manually pushed to - lawcus.com
- **develop** - automatically pushed to - dev.lawcus.com or develop.lawcus.com or something like this
- **release** - automatically pushed to - release.lawcus.com (this branch and subdomain should apear only during release)

*Also it would be great to automatically create/delete subdomain for each new created branch like task-some-title-32.lawcus.com so we can test the particular feature/bug fix. But it can be not realistic due to server limitations on subdomains or some technical issues, I’m not sure.*
