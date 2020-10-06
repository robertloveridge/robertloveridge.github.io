---
layout: post
title:  "Remove the history from a GitHub repo"
date:   2020-09-20
categories: development
---

To remove all commit history from your repository while retaining the current code state, follow the steps below. This is handy if you've made a complete mess of your commit history and want to start fresh!

### Checkout a new branch

While in the 'master' branch, checkout a new and orphaned branch called 'latest_branch'.

```
[user@server ~/Projects/App (master)]$ git checkout --orphan latest_branch

Switched to a new branch 'latest_branch'
```

### Add all the files

```
[user@server ~/Projects/App (latest_branch)]$ git add -A
```

### Commit the changes

```
[user@server ~/Projects/App (latest_branch)]$ git commit -am "commit message"

[latest_branch (root-commit) 46d1b1f] Initial commit
```

### Delete the old 'master' branch

```
[user@server ~/Projects/App (latest_branch)]$ git branch -D master

Deleted branch master (was a91ea41).
```

### Rename 'latest_branch' to 'master'

```
[user@server ~/Projects/App (latest_branch)]$ git branch -m master
```

### Finally, force update your remote repository

```
[user@server ~/Projects/App (master)]$ git push -f origin master
```