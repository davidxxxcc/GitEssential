# This chapter shows how to edit and commit file on Git

### Let's say we have three different files and now we make some text changes on these files.

![](/assets/file)

Check working place status

`git status`

![](/assets/checkStatus)

Now you can see three files are marked with red and not stage for commit

Let stage all the files

`git add .`

Or if you want to stage specified file you can

`git add first_file.text`

In this case, we stage all of the files

![](/assets/stageAll)

And let's commit these files.

`git commit -m "Make change to first, second and third files"`

![](/assets/commitAll)

Done!

Let's check the git status

Awesome!

![](/assets/checkGit)

