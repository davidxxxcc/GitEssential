This chapter shows how to delete file on Git

Let's create two files to delete

![](/assets/deleteFile)

Stage and commit these two files

`git add .`

`git commit -m "Adding 'red shirt' files"`

Now if we manually delete \_file\_to\_delete1 \_and check git status again

`git status`

![](/assets/gitDeleteManually)

Now we need to tell git that \_file\_to\_delete1 \_has been deleted

`git rm file_to_delete1`

\(below just demo _file\_to\_delete3_\)

![](/assets/gitdelete2)

