---
title: "How to work with multiple git branches simultaneously."
datePublished: Sun Jan 21 2024 17:09:57 GMT+0000 (Coordinated Universal Time)
cuid: clrnr7nev000109jl8id8265j
slug: how-to-work-with-multiple-git-branches-simultaneously
tags: git, tips

---

If you've faced this situation before, you might want to learn this.

---

You're working on feature A at your work and suddenly you got a ping on Slack.

*"Please fix this bug, it's causing a critical bug in production that needs fixing ASAP!!!"*

You git stash whatever changes you have right now to make sure the working directory is clean, git checkout to the master branch, make the fix, and when you're done, you git stash pop to continue your work where you left off.

Or worst, you git commit -m "WIP" because you don't know how to git stash. 🥲

---

If you're perfectly happy with you current git workflow, you can stop reading here.

But if you want to know a better way (hopefully) to work with multiple branches in git at the same time, continue reading.

# Introducing Git Worktree.

While stashing your changes and popping them back up is a perfectly valid way to temporarily save your progress (that's how I previously did it too), I'd argue there's a better way to handle it.

Git worktree allows you to "spawn" a new branch that you can change, stage, and commit without ever needing to do a weird hack just to work with 2 branches at the same time.

Git worktree has 3 commands

* `git worktree list`
    
* `git worktree add <branch name>`
    
* `git worktree remove <branch name>`
    

I think from the commands above, it's pretty self explanatory.

Now let's imagine you're in the same situation described above.

Knowing git worktree, you can now just run `git worktree add master` to create a new branch in your current directory.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Go ahead and try it on any of your code repository.</div>
</div>

You'll notice that there's a new folder called "master" in your root directory. When you `cd master` into it in your terminal, you're now in the master branch of your same project, without ever leaving your feature branch.

If you're on VS Code, you'll also notice that VS Code detects there's now 2 different branches running.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705855874396/f3110215-f4e6-45ed-b437-719aa6bb2997.png align="center")

Congratulations, you are now working on 2 different branches of the same project at the same time.

Feel free to spawn more branches as needed but make sure to delete them once you're down with it.

# Some downsides.

After using worktree for a while now for my work, there's 1 minor downside using git worktree that I want to highlight.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705856250625/fbc0dd38-cff3-40d2-90cd-a7931be65015.png align="center")

As you can see, when you want to search for a snippet, the result shows both the main directory and the "new" repo you've created.

To solve this in VS Code, you can just exclude the "main" directory like this 👇

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705856446173/e5c60d9f-c33d-4f2d-b2d3-45e3b33c64a4.png align="center")

Now the search only shows 1 result instead of 2.

This is a pretty minor downside but it's something I figured I should point out.

Other than that, I think git worktree is fun to use and work with and I think you should give it a try.

Thanks for reading!