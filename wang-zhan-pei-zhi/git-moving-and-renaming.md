This chapter shows how to moving and renaming files on Git

Let's say if we want to rename first\__file1.txt to primary\__file.txt

![](/assets/rename)

Now you will notice that Git will treat this action as delete _first\_file.txt_

`git status`

![](/assets/GitRenameCheck)

Therefore, we can add primary\__file.txt on stage and remove first\__file.txt using follwing command



