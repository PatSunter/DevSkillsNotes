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

Setting up ssh access:
----------------------

 * Update the relevant ssh-keys on github
 * if you want, test with: https://help.github.com/articles/testing-your-ssh-connection/
 * Update your remotes to use ssh rather than https, e.g.::

  git remote set-url origin git@github.com:PatSunter/DevSkillsNotes.git

Refs:
-----

 * http://stackoverflow.com/questions/3611256/forking-vs-branching-in-github
 * http://qsapp.com/wiki/Github

