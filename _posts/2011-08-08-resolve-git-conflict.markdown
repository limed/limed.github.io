---
layout: post
title: "Resolving git conflicts"
---

If you do a rebase or a pull and it has a merge conflict do the following

1. Check for file that is having conflict

    ```git status```

2. Edit code that has conflict and git add

    ```git add -a```

3. Commit edit

    ```git commit -am "Some message"```
