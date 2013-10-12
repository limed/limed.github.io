---
layout: post
title: "Deleting special character files in UNIX"
---

If you're an idiot like me and managed to create a file with special characters like ```--exclude=*.svn``` and need to remove it, here's how

```bash
    rm ./'--exclude\=\*.svn'
```

Remember don't be an idiot like me
