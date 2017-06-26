---
layout: post
title:  "Troubleshooting Eclipse: duplicate IDs while saving preferences"
date:   2017-06-26 16:22:00 -0300
categories: eclipse troubleshoot
---

I had some (annoying) error today in my Eclipse instances: Every time I change something in the IDE preferences, the following message appeared and the preferences were rolled back after an restart.  

```
An internal error occurred during: "Store preferences".
Duplicate ID: syncXXX
```

... where XXX is some integer.

After some googling, I found a [non-related bug description](https://bugs.eclipse.org/bugs/show_bug.cgi?id=494684) that helped me to resolve this issue.

Easily: just remove the file `user.setup` file in `~/.eclipse/org.eclipse.oomph.setup/setups`.

```bash
rm ~/.eclipse/org.eclipse.oomph.setup/setup/user.setup
```

The removed file will be recreated in the next start. You will need to set all the recently changed preferences, but the preferences synchronization will work again.
