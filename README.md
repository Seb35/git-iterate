git-iterate
===========

If you have to repeat a same Git operation over a bunch of subdirectories (e.g. 'status' or 'branch -vv'), this small Git addon is dedicated to this task.

Examples:
```
git iterate -- status
git iterate -q mydir1 mydir2 -- fetch --all
```

Syntax
------

General syntax:
```
git iterate [-q|--quiet] [DIR1] [DIR2] [DIRS...] -- SUBCOMMAND [OPTIONS]
```

* -q: [optional] Remove all non-error output
* --quiet: [optional] Remove the names of the directories in which Git is currently running
* DIR1, DIR2, ...: [optional] Subdirectories names where the Git subcommand must be run, by default current directory
* SUBCOMMAND [OPTIONS]: classical Git subcommand ('status', 'fetch --all', 'pull', etc.)

License
-------

* License: WTFPL 2.0
* Author: Seb35 - Sébastien Beyou
