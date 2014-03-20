git-fff
=======

Git fast-fast-forward - ff a branch without checkout.

Usage
-----

````
git fff <branch> [<committish-to-merge>]
````

If <committish-to-merge> is not given, it will default to HEAD.

Description
-----------

I once wanted to fast-forward master to tested revision from dev branch, but had a dirty working tree.
The usual workaround is like this:
````
stash; checkout master; merge --ff-only tested_revision; checkout dev; stash pop;
````

I wanted something that doesn't require typing 5 command nor unnecessary data shuffling (stashing, which is pretty much pointless in this case).

This script is basically wrapper for git update-ref that makes fast-forwardness sanity-check and fallbacks to merge --ff-only in corner case of fff'ing current branch. That's it ^ ^.

Zsh completion
--------------

Zsh completion script included, make sure to put it in some directory in your $fpath.
