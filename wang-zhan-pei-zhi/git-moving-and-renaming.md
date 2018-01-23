This chapter shows how to moving and renaming files on Git

Let's say if we want to rename first\_\_file1.txt to primary\_\_file.txt

![](/assets/rename)

Now you will notice that Git will treat this action as delete _first\_file.txt_

`git status`

![](/assets/GitRenameCheck)

Therefore, we can add primary\_\_file.txt on stage and remove first\_\_file.txt using follwing command



![](/assets/addRevmoe)

