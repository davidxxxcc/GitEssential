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

### Amending commits

![](/assets/4)

