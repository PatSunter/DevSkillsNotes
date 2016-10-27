
Useful git cmd-line options:
----------------------------

Equivalent to svn log -v to show filenames of changed files::

  git log --name-only

Git - configuration, global and local:
--------------------------------------

To set a global email address::

  git config --global --set user.email email@address.com

To set a local email address (e.g. a different github one
compared to your work one)::

  git config --local --set user.email email@address.com

To edit one of these config files (replace local/global as 
needed)::

  git config --local -e

Git - checking branches on a remote:
------------------------------------

To see more info on a configured remote, including branches::

  git remote show remote_name

Git - controlling push to different remotes:
--------------------------------------------

Pushing to e.g. a gerrit code-review remote::

  git push gerrit HEAD:refs/for/master 

(Pushing to the master branch, else use refs/for/$BRANCH)

Git - modifying the last commit:
--------------------------------

Basic editing of last commit msg (if you haven't staged other changes)::

  git commit --amend

Editing the author (E.g. if you didn't set email for a repos correctly)::

  git commit --amend --author="Author Name <email@address.com>"

Undoing a commit for more extensive changes, then redo::

 git reset HEAD~
 <<edit files as necessary>>
 git add ...
 git commit -c ORIG_HEAD

(With thanks to http://stackoverflow.com/questions/927358/how-to-undo-last-commits-in-git)

Git - modifying other earlier commits (rebase):
-----------------------------------------------

Recommended approach is to use git rebase --interactive.

http://stackoverflow.com/questions/1186535/how-to-modify-a-specified-commit-in-git

"You can use git rebase, for example, if you want to modify back to commit bbc643cd, run"::

 $ git rebase --interactive 'bbc643cd^'

