MDC - Multi Destinations Copier by Martial Demolins
Version: 1.0
License: GPL v3+ (https://www.gnu.org/licenses/gpl-3.0.txt)
Source + download page: https://github.com/Folcogh/MDC (or, for TP users, \Partage_Techniciens\Demolins\Softs\MDC)
Bug reports and suggestions: martial <dot> demolins <at> gmail <dot> com


How to
======

This program is intended to clone a content into multiple drives (like redistributable USB sticks)
1. Select a source directory (or drag a directory on the program icon)
2. Select the destinations drives to be cloned, then click the Clone button
3. Check the diff dialog, showing what will be deleted or copied/overwritten
4. Click the Clone button to start the process

/!\ Warning: No consistency check is performed about source and destinations:
/!\
/!\ - you can try to clone a source on itself
/!\ - you can remove an USB stick after the diff is displayed, then start the cloning process
/!\ - you can delete or move the source directory after analysis
/!\ - and certainly many other stupid things
/!\
/!\ => the program won't crash, but you could get into data loss. Please don't complain about your own mistakes or stupidity


Features
========

- directories are cloned, even if they are empty
- files are deleted if necessary, ignored if the source and destination names match, or copied to the destination if they are not present
- by design, files are overwritten in the destination if they size is < 2Mb. It allows the cloner to modify some small data files and ensure they are cloned, without breaking performance


Under the hood
==============

Written in C++, statically built on Windows against Qt 5.12.3
Sources are provided with a .pro file, so you can easily rebuld the program.
See https://www.qt.io/ for infos.

This version separates UI factory and data processing: analyze and clone process are run in external threads,
which allows to keep UI smouth, usable, while processes are interruptable