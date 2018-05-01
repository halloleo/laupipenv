# laupipenv - LAUnch Python script In Pipenv virtual ENVironment

Small (shell) wrapper which makes sure that the [Pipenv][] environment
of a Python project is activated before running the Python
script. 

This is good for scripts which should run straight from the command
line and **it works even if the launcher wrapper is in a synced
(Dropbox?) folder accessed by different machines with different
locations for the virtual environment**.

## `laupipenv_general`

The file `laupipenv_general` has to be renamed to the filename of the
Python script without the extension and a symbolic link to this file
should be placed in one of the PATH directories. Now the command can
be called straight from the command line.

**Example**

> In the project directory `/path/to/me/listmycmds` is a Python
file `listmycmds.py`. Then the file `laupipenv_general` has to be placed
in `/path/to/me/listmycmds` with the name `/path/to/me/listmycmds` (no
extension). Then symlink this file listmycmds to `$HOME/bin/listmycmds`.


## `laupipenv_fixed`

`laupipenv_general` works by finding the Pipenv environment of the
project via `pipenv --venv`. This is surprisingly slow. To speed up
invocation of your Python script you can har-code the location of the
environment. `laupipenv_fixed` is template for this.

In order to provide compatibility with Dropbox access from different
machines the different locations for the virtual environment are in
this case managed by:

* a machine-dependent environment variable `WORKON_HOME` 

and

* a hard-code name of the virtual environemnt. This name has to be the same on all machines

The environment variable `WORKON_HOME` has to be declared in one of the bash startup scripts. `WORKON_HOME` might be set already if you use [Virtualenvwrapper][]; teh variable points to the parent directory of all virtual environments.

The name of the environment to activate is then hard-coded in the `laupipenv_fixed` warp per. This wrapper has to renamed in the same way as explain above for `laupipenv_general`.


[Pipenv]: https://docs.pipenv.org/
[Virtualenvwrapper]: http://virtualenvwrapper.readthedocs.io/

<!--  LocalWords:  listmycmds laupipenv Pipenv
 -->

