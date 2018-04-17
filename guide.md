# git stash

比较常见的几个应用场景:  
### Pulling into a dirty tree
           When you are in the middle of something, you learn that there are upstream changes that are possibly relevant to what you are doing. When your local changes do
           not conflict with the changes in the upstream, a simple git pull will let you move forward.

           However, there are cases in which your local changes do conflict with the upstream changes, and git pull refuses to overwrite your changes. In such a case, you
           can stash your changes away, perform a pull, and then unstash, like this:

               $ git pull
                ...
               file foobar not up to date, cannot merge.
               $ git stash
               $ git pull
               $ git stash pop

### Interrupted workflow
           When you are in the middle of something, your boss comes in and demands that you fix something immediately.
           You can use git stash to simplify the above, like this:

               # ... hack hack hack ...
               $ git stash
               $ edit emergency fix
               $ git commit -a -m "Fix in a hurry"
               $ git stash pop
               # ... continue hacking ...
               
--------------------------------       
[ERROE]. error: Your local changes to the following files would be overwritten by merge:

	xxxxxxxxxxxxxx        

   Please commit your changes or stash them before you merge.
Aborting

-------------------------
