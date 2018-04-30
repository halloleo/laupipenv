# PYthon IN Virtual environment

Small (shell) wrapper which makes sure that the environment of a
Python project is activate before running the project file.

The file `pyinv_general` has to be rename to the filename of the
python project without the extension and a symbolic link to this file
should be placed in one of the PATH directories.

Example: In the project directory `/path/to/me/listmycmds` is a Python
file `listmycmds.py`. Then the file `pyinv_general` has to be placed
in `/path/to/me/listmycmds` with the name `/path/to/me/listmycmds` (no
extension). Then link this file listmycmds to `$HOME/bin`.

<!--  LocalWords:  listmycmds pyinv
 -->
