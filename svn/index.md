# Subversion cheatsheet


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

## Table of Contents
- [SVN](#SVN)



### SVN
* Checkout a repository ```svn co https://svn.elznic.net/janelznic```
* Update repository ```svn up```
* Commit changed files ```svn ci –m "#TICKET Commit message"```
* Show changes ```svn status``` or ```svn st```
* Add file to repository ```svn add index.html```
* Delete a file from repository ```svn rm debug.log```
* Show current revision ```svn version```
* Add keywords to files ```svn propset svn:keywords "Id Rev Author" <soubory>```
* List a log ```svn log | less```
