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

`95bede780b1342c3b880b`is the commit you want to reverse

`git revert 95bede780b1342c3b880b`

### Using reset to undo commits

Chinese version

https://dotblogs.com.tw/wasichris/2016/04/29/225157

It's also very dangerous. The command that we're going to be using is git reset. What git reset does is it allows us to specify where the HEAD pointer should point to.

* soft
  * Soft is going to move the HEAD pointer to the specified commit, and it's not going to change the staging index, or the working directory at the same time. It's just going to move the pointer. It's the safest of all these options, that's why it's called soft. Just a soft reset, move the pointer and do nothing else. 
  * `git reset --soft da38660bbcd20`
  * ![](/assets/soft)
* mixed
  * This is in between soft and hard which is why it's called mixed, and it is the default. What it does is it moves the HEAD pointer to the specified commit, and it also changes the staging index to match the repository.
  * It does not change your working directory though. So, at this point, the staging index and the repository will be set in one place, our working directory, though, has all those changes that we've made. All the things that were in later versions of the repository are still in our working directory.
  * `git reset --mixed da38660bbcd206a`
  * ![](/assets/mixed)
* hard
  * And then the last one is the most destructive of all, and that is hard. A hard reset will not only move the pointer of the repository, but it will make your staging index and your working directory match that as well.

![](/assets/reset)

