
Useful git cmd-line options:
----------------------------

Equivalent to svn log -v to show filenames of changed files::

  git log --name-only

Git - controlling push to different remotes:
--------------------------------------------

Pushing to e.g. a gerrit code-review remote::

  git push gerrit HEAD:refs/for/master 

(Pushing to the master branch, else use refs/for/$BRANCH)

General workflow:
-----------------

Seems there are a couple of main Git workflows:

1) All be collaborators on one project, but maintain multiple streams of
   development using Branches.

2) Have a "main" repo (and call it 'upstream' locally) for overall project
   , and also a local repo you commit to (call it 'origin')
   
   Commit your changes to branches on your 'origin' repo, then when you 
   have functionality wish to merge into the main repo, use a "pull request"
   to ask maintainer to pull, review, then merge in.

Refs:
-----

 * http://stackoverflow.com/questions/3611256/forking-vs-branching-in-github
 * http://qsapp.com/wiki/Github

