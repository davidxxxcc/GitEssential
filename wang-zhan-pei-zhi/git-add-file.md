# This chapter illustrate how to add file to git

Check status of git

`git status`

![](/assets/import7.png)

### Now let's manually add two files in our working directory 

check git status

`git status`

![](/assets/import8.png)

Let's say if we only want to stage one file

As we can see, now seond\_\_file.text is on stage while third\_\_file.text is still untracked.

`git add second_file.text`

`git status`

![](/assets/import9.png)

Now we want to commit second\_file.text

`git commit -m "Add second file to project"`

![](/assets/import10.png)

