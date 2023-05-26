---
title: "How To Squash Commits Locally"
datePublished: Fri May 26 2023 07:05:52 GMT+0000 (Coordinated Universal Time)
cuid: cli47ycl6001a09l76p0z4owy
slug: how-to-squash-commits-locally
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685084799709/a94ec6d2-78d8-4cbf-92a2-69049d6d8091.webp
tags: tutorial, github, opensource, version-control, git

---

If you're like me, you're probably familiar with "squash and merge" when merging pull requests on GitHub.

If you're also like me, you're now trying to figure out how to do this seemingly simple "squash and merge" thingy locally for some reason.

Whether you've been asked to do it because that's how your team has done it (read: my team) or you're curious how to do it just to learn – you've come to the right place.

# The Mechanism

The main idea of squashing your commits is you need to reset or undo your commits until the very last one you want to squash. Then just git commit again.

### **1\. Reset to your last N commit**

Where, N = number of commits you want to squash

For example, if you have 3 commits that you want to squash, you can simply `git reset --soft HEAD~3`

**IMPORTANT**: make sure it's a \**soft\** reset by using the `--soft` flag.

Otherwise, you will lose all of your progress. We don't want that.

### **2\. Re-commit**

This is pretty straightforward, just `git commit -m ...`

---

And that's it, it's pretty simple when you know now but it was quite confusing if you're used to the 1-click squash and merge button on GitHub.

At least that was the case for me. 🥲