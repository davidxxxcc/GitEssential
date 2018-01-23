# This chapter shows how to undo changes on Git

### Undo working directory files

Let's say if we accidentally delete part of text on \_index.html \_and we want to recover from copying repo to working directory

![](/assets/2)

`git checkout -- index.html`

![](/assets/1)

### Unstaging files

If you put something into the staging area that you don't want there, you can take it out by using git reset HEAD, and the status message will help you remember that.

`git reset HEAD resource.html`

![](/assets/3)

### Amending commits \(only the latest one\)

if we make a change to this, even if we just change the commit message, it's going to change that SHA to be something different, and if that SHA becomes something different, well, now the parent of snapshot C will need to be changed as well, because it needs to point to something different. And if we change the parent of snapshot C, well then when we run it through the algorithm it's going to come up with a different SHA as well.

So all the way down the chain every single Git object will have to be changed just because we've made a change earlier down the line. Well, if completely broken the integrity of the data that's in Git. So Git doesn't want us to do that. However, it is possible for us just to change the last commit, because nothing depends on it yet. So the most recent commit the commit that HEAD points to we do have the ability to edit. Once we've tacked another on to the end of that we can't edit in anymore, but the one at the end is still editable, and we can do that using the amend option.

![](/assets/4)

`git commit --amend -m "Adjust list items"`

### Reverting a commit

What the Revert command will do is it will take all of the changes that were there, and it will flip them around. It will do the exact opposite of those changes.

`95bede780b1342c3b880b `is the commit you want to reverse

`git revert 95bede780b1342c3b880b`

