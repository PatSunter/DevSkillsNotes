
Checking other shared libraries references by a library currently (Note: relies on your LD_LIBRARY_PATH)::

  ldd /path/to/lib.so

Checking symbols exported by a library::

  nm -D /path/to/lib.so

Refs:

 * http://stackoverflow.com/questions/1237575/how-do-i-find-out-what-all-symbols-are-exported-from-a-shared-object
