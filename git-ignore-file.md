```

I got into this situation a few times, so I made a one-liner I can paste into terminal.

touch .gitignore && echo "node_modules/" >> .gitignore
When I've added the node_modules folder to git already

git rm -r --cached node_modules && touch .gitignore && echo "node_modules/" >> .gitignore
Explanation

touch will generate the .gitignore file if it doesn't already exist.

echo and >> will put node_modules/ at the end of .gitignore, causing the node_modules folder and all subfolders to be ignored.

git rm -r --cached removes the node_modules path from git control. The flags cause the removal to be recursive and include the cache.


```



