
Useful git cmd-line options:
----------------------------

Equivalent to svn log -v to show filenames of changed files::

  git log --name-only

Git - controlling push to different remotes:
--------------------------------------------

Pushing to e.g. a gerrit code-review remote::

  git push gerrit HEAD:refs/for/master 

(Pushing to the master branch, else use refs/for/$BRANCH)


