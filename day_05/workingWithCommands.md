# Linux Command Line Notes (Part I - Chapter 5: Working with Commands)

This chapter covers how commands work in Linux and how the shell interprets user input.

The goal is to understand where commands come from, how to inspect them, and how to use command history and shortcuts efficiently.

Linux commands are not magic. The shell searches for executable programs using defined paths and executes them.

## type

type shows how the shell interprets a command.

Example:
type ls

Possible results:
- executable program
- shell builtin
- alias

Example:
type cd

cd is usually a shell builtin, not a standalone program.

## which

which shows the path of an executable.

Example:
which ls

Possible output:
/usr/bin/ls

This helps identify which program will run when a command is executed.

## help

help displays help information for shell builtins.

Example:
help cd

Useful for commands built directly into the shell.

## man

man opens manual pages for commands and programs.

Example:
man ls

Navigation inside man:
- arrows or PageUp/PageDown to scroll
- / to search
- q to quit

Manual pages are one of the main Linux documentation systems.

## apropos

apropos searches manual page descriptions.

Example:
apropos copy

Useful when you know what you want to do but not the exact command name.

## history

history shows previously executed commands.

Example:
history

Commands from history can be reused instead of typing them again.

Run a previous command:
!42

Run previous command:
!!

History saves time and reduces repetitive typing.

## command line editing

The shell supports command editing shortcuts.

Examples:
Ctrl + A   move to beginning of line
Ctrl + E   move to end of line
Ctrl + U   delete before cursor
Ctrl + K   delete after cursor

These shortcuts improve terminal efficiency significantly.

## alias

alias creates command shortcuts.

Example:
alias ll='ls -l'

Temporary aliases exist only for the current shell session unless added to shell configuration files.

## clear

clear cleans the terminal screen.

Example:
clear

Useful when terminal output becomes cluttered.

## summary

type explains how the shell interprets commands.

which shows executable locations.

help and man provide documentation.

history stores previous commands.

aliases create shortcuts.

Shell editing shortcuts improve command line efficiency.

## philosophy

Efficient Linux usage is not about memorizing hundreds of commands.

It is about learning how to inspect, discover, and reuse commands intelligently.