
Showing values of long C strings or large arrays:
-------------------------------------------------

http://stackoverflow.com/questions/233328/how-do-i-print-the-full-value-of-a-long-string-in-gdb

A: Modify the value of print elements:
e.g.::

    set print elements 10000

B: Use the puts function e.g.::

    call puts(mystring)
