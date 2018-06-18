---
layout: default
status: publish
published: false
title: "Command line tappas: Ammending a commit"
---

Sometimes you have a bunch of commits on a branch and want to ammend to a previous commit.

It works like this.

Just commit your code like so

	git add .
	git commit -m “ammend me”

Then you can rebase to master:

	git rebase -i master

And editor will open that displays the list of your commits.

Just move your “ammend me” commit below the commit you want to ammend to and add change `pick` to `fixup`.

The whole process looks like this.



