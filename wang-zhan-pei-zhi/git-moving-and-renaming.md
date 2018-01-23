# This chapter shows how to moving and renaming files on Git

Let's say if we want to rename first\_\_file1.txt to primary\_\_file.txt

![](/assets/rename)

Now you will notice that Git will treat this action as delete _first\_file.txt_

`git status`

![](/assets/GitRenameCheck)

Therefore, we can add primary\_\_file.txt on stage and remove first\_\_file.txt using follwing command

`git add primary_file.txt`

`git rm first_file.txt`

![](/assets/addRevmoe)

Let's check the git status again

`git status`

Now git realize that it's a rename action

![](/assets/checkagain)

Another way to rename file to using move command

If we want to rename second\_\_file.txt to secondary\_\_file.txt

`git mv second_file.txt secondary_file.txt`

![](/assets/move)

Let's check git status again

git status



