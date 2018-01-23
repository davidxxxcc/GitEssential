# This chapter illustrates how to review file changes.

On working directory

### Let's say we edit first\_file.txt and we want to check where we amend the texts

`git diff`

![](/assets/gitDiff)

If we also amend third\_file.txt and check again

`git diff`

![](/assets/gitDiffAll)

We can specified one file to review the difference

`git diff first_file.txt`

![](/assets/gitDiffOneFile)

On stage directory

Let's say we edit first\_file.txt and we want to check where we amend the texts

`git diff --staged`

![](/assets/gitDiffStaged)

