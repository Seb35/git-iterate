git-iterate
===========

If you have to repeat a same Git operation over a bunch of subdirectories (e.g. 'status' or 'branch -vv'), this small Git addon is dedicated to this task.

Examples:
```
git iterate -- status
git iterate -q dir1 dir2 -- fetch --all
git iterate -q dir1 dir2 foreach myscript.sh
```

Syntax
------

### General syntax:
```
git iterate [-q|--quiet] [DIR1] [DIR2] [DIRS...] -- SUBCOMMAND [OPTIONS]
```

* -q: [optional] Remove all non-error output
* --quiet: [optional] Remove the names of the directories in which Git is currently running
* DIR1, DIR2, ...: [optional] Subdirectories names where the Git subcommand must be run, by default current directory
* SUBCOMMAND [OPTIONS]: classical Git subcommand ('status', 'fetch --all', 'pull', etc.)

### Non-Git commands:
```
git iterate [-q|--quiet] [DIR1] [DIR2] [DIRS...] foreach SHELLCOMMAND [OPTIONS]
```

* -q: [optional] Remove all non-error output
* --quiet: [optional] Remove the names of the directories in which Git is currently running
* DIR1, DIR2, ...: [optional] Subdirectories names where the Git subcommand must be run, by default current directory
* SHELLCOMMAND [OPTIONS]: general shell command to be executed in Git directories ('ls', etc.)

License
-------

* License: WTFPL 2.0
* Author: Seb35 - Sébastien Beyou

Contribute
----------

Although this is a small program, any contribution is welcome! Please [open an issue](https://github.com/Seb35/git-iterate/issues) to discuss ideas or bugs, or even [submit pull requests](https://github.com/Seb35/git-iterate/pulls) to propose implementations.

This is a small nice-to-do list:
* test in various environments -- I only tested it on Debian
* improve documentation
* write unit tests
