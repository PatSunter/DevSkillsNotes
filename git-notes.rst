
git logging:
------------

Equivalent to svn log -v to show filenames of changed files
and status::

  git log --name-status

Or to just show names of files::

  git log --name-only

To show changes to a specific file with each revision::

  git log -p /path/to/file

Git - configuration, global and local:
--------------------------------------

To set your name::

  git config --global user.name "my name"

To set a global email address::

  git config --global --set user.email email@address.com

To set a local email address (e.g. a different github one
compared to your work one)::

  git config --local --set user.email email@address.com

To edit one of these config files (replace local/global as 
needed)::

  git config --local -e

Git - configure global ignores:
-------------------------------

See https://help.github.com/articles/ignoring-files/

Steps:

 # Create, edit, save a global gitignore file, e.g. ~/.gitignore_global
 # Run the following::

     git config --global core.excludesfile ~/.gitignore_global

Git - branches, remote to local
-------------------------------

To see more info on a configured remote, including branches::

  git remote show remote_name

To check out a remote branch locally, and set tracking (e.g.
assume remote 'origin', with existing branch 'test')::

  git checkout -b test origin/test

(For more see http://stackoverflow.com/questions/1783405/how-to-check-out-a-remote-git-branch)

Interactive git tools (esp history checking):
---------------------------------------------

 * gitk - built-in repo browser, see https://git-scm.com/docs/gitk
 * Other GUI tool ideas: https://git-scm.com/download/gui/linux

Git - tagging:
--------------

Creating annotated (signed) tags
""""""""""""""""""""""""""""""""

Create annotated tags with::

  git tag -m"tag annotation" <tagname>

e.g.::

  git tag -m"Version 2.0.0rc4" v2.0.0rc4

(Need to have PGP account etc created first to do the annotated messages).

Git - printing all tags info, e.g. date created:
""""""""""""""""""""""""""""""""""""""""""""""""

For annotated tags use::

  git for-each-ref --sort=taggerdate --format '%(refname) %(taggerdate)' refs/tags

Or to also print authors::

  git for-each-ref --sort=taggerdate --format '%(refname) %09 %(taggerdate) %(subject) %(taggeremail)' refs/tags

(Via http://stackoverflow.com/questions/6269927/how-can-i-list-all-tags-in-my-git-repository-by-the-date-they-were-created)

Git - controlling push to different remotes:
--------------------------------------------

Pushing to e.g. a gerrit code-review remote::

  git push gerrit HEAD:refs/for/master

(Pushing to the master branch, else use refs/for/$BRANCH)

Adding for commit only part of a file (--patch):
------------------------------------------------

For adding only part of a file for committing::

  git add --patch filename.x

Will bring up interactive prompt for hunks, useful options other than
y/n::

  a: this hunk and all later hunks
  q: quit, not this hunk and exit.

Press ? for help, or see http://stackoverflow.com/questions/1085162/commit-only-part-of-a-file-in-git

Note, can use git diff --staged to see what's staged for committing.

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

Re-check out a branch from remote, ignore local commits:
--------------------------------------------------------

To check out a remote branch and abandon local commits::

 git reset --hard origin/branch

Git - modifying other earlier commits (rebase):
-----------------------------------------------

Recommended approach is to use git rebase --interactive.

http://stackoverflow.com/questions/1186535/how-to-modify-a-specified-commit-in-git

"You can use git rebase, for example, if you want to modify back to commit bbc643cd, run"::

 $ git rebase --interactive 'bbc643cd^'

After changing a commit you picked to edit, do `git commit --amend`.
Once happy, do `git rebase --continue`.

Breaking a previous commit into several (using rebase)
------------------------------------------------------

To break a prev commit into several::

   git rebase --interactive

Select commit to break up, mark as e (edit).
Once it rewinds to selected commit::

  git reset HEAD~

This will make all previously-committed changes marked as
merges (M) / new files, and you can then go ahead and
add/commit as new commits.

(Note:- use 'git commit' rather than 'git commit --amend'
 as is normally done when fixing an existing commit during
 rebase).

https://stackoverflow.com/questions/6217156/break-a-previous-commit-into-multiple-commits

Combining multiple commit-histories using rebase rather than merge
------------------------------------------------------------------

To avoid a lot of code merges in the history (especially when changes
are non-conflicting but e.g. you commit to your local repo before
updating) - you can use the git rebase command.

Default is fairly simple, just::

  git rebase

More advanced use listed above.

Diff against a stash
--------------------

See: http://stackoverflow.com/questions/7677736/git-diff-against-a-stash

To diff against the first stash::

    git stash show -p stash@{0}
