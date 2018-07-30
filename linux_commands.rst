

Using find and xargs in combination:
------------------------------------

A little add-on: actually there is a method for doing what you're trying to accomplish. Just execute a shell session passing the command with option -c. The following example should work:

Code:: 

  find trunk/ -type f -not -path '*.svn*' -exec bash -c 'diff "{}" `echo "{}" | sed "s/^trunk\///"`' \;

http://www.softpanorama.org/Tools/Find/using_exec_option_and_xargs_in_find.shtml
