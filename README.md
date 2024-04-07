git-iterate
===========

If you have to repeat a same Git operation over a bunch of subdirectories (e.g. 'status' or 'branch -vv'), this small Git addon is dedicated to this task.

Examples:
```
git iterate -- status
git iterate -q dir1 dir2 -- fetch --all
git iterate -q dir1 dir2 foreach myscript.sh
```

WARNING: the parameters names and exact features may change, this tool is not in a "stable" state given it evolves according to my own needs. Feedback about the parameters names and their associated features are welcome.

Syntax
------

### General syntax:
```
git iterate [-q|--quiet] [<dir>...] -- <command>
```

* -q: [optional] Remove all non-error output
* --quiet: [optional] Remove the directory names in which Git is currently running
* <dir>...: [optional] Subdirectories names where the Git subcommand must be run, by default current directory
* <command>: standard Git command and parameters ('status', 'fetch --all', 'pull', etc.)

### Non-Git commands:
```
git iterate [-q|--quiet] [<dir>...] foreach <shellcommand>
```

* -q: [optional] Remove all non-error output
* --quiet: [optional] Remove the directory names in which Git is currently running
* <dir>...: [optional] Subdirectories names where the Git subcommand must be run, by default current directory
* <shellcommand>: general shell command to be executed in Git directories ('ls', etc.)

License
-------

* License: WTFPL 2.0
* Author: Seb35 - Sébastien Beyou

Contribute
----------

Although this is a small program, any contribution is welcome! Please [open an issue](https://github.com/Seb35/git-iterate/issues) to discuss ideas or bugs, or even [submit pull requests](https://github.com/Seb35/git-iterate/pulls) to propose implementations.

Here are some ideas for possible improvements.

Quality:
* test in various environments - I only tested it on Debian
* still improve documentation?
* write unit tests
* package - for DEB, RPM, …
* translate the documentation
* get some user feedback about the CLI interface, and amongst others: the quiet options

Bugs:
* detect if bold is supported and possibly how: 1. if no bold is supported it should be deactivated, for instance in non-console outputs or non-compatible consoles; 2. I saw "echo -e" must be used for Bash but "echo" must be used for sh.

Features:
* add an option to use non-bold for the directory names?
* add a special syntax `git iterate [<dir>...]` to only display Git directories?
* add an option to stop on first error, on first output? use a non-zero exit code in this case?
* add an option to explicitely search Git directories inside Git directories? or make it the default behaviour (will be longer in this case)?
