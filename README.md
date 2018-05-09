`opendifftool` is a drop-in replacement for Apple command-line tool `opendiff`, geared toward being a better diff or merge tool for git. Indeed, `git difftool --tool=opendiff` suffers from two shortcomings:

- opendiff opens a window in the Filemerge application and then immediately exits. As a result, when several files have been modified, `git difftool` results in several windows being opened in slow succession, interrupting the examination of the current window when a new one opens, and thus forcing the user to wait until they are all up.

- git stores the contåents to be compared in file with names starting with a random prefix, which makes the window title less legible than they should be.

This program solves both problems: it exits only when the Filemerge window is closed; and it renames the files created by git, putting them in a directory whose last component reads either BEFORE or AFTER to clearly show what is compared to what.