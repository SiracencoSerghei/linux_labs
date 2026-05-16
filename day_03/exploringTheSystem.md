# Linux Command Line Notes (Part I - Chapter 3: Exploring the System)

This chapter covers how to inspect files and directories, understand their contents, and explore the Linux filesystem beyond simple navigation.

The goal is to learn what exists on the system and what type of data you are looking at.

## file

The file command shows what type of data a file contains.

Example:
file /etc/passwd

It does not rely on extensions. Instead, it analyzes actual file content.

Examples of output:
- text file
- directory
- executable
- symbolic link

This is useful because Linux does not trust filenames.

## less

less is a pager used to view long text files.

Example:
less /etc/services

Inside less:
- arrows to scroll
- / to search
- q to quit

It allows safe viewing of large files without opening them in an editor.

## /etc directory

The /etc directory contains system configuration files.

Examples:
- /etc/passwd (user accounts info)
- /etc/hosts (hostname mapping)
- /etc/fstab (filesystem mounts)

This is one of the most important directories in Linux systems.

## /var directory

The /var directory contains variable data that changes during system operation.

Examples:
- logs
- cache
- spool files

Common example:
- /var/log contains system logs

## /usr directory

The /usr directory contains user-related programs and data.

Examples:
- /usr/bin (user commands)
- /usr/lib (libraries)
- /usr/share (shared resources)

Most installed software lives here.

## symbolic links

A symbolic link is a shortcut to another file or directory.

Example:
ls -l /bin

You may see arrows like:
/bin -> /usr/bin

This means /bin is pointing to another location.

## viewing file content

Basic tools:
cat file.txt   (prints full content)
less file.txt  (scrollable view)
head file.txt  (first lines)
tail file.txt  (last lines)

These tools help inspect files without editing them.

## summary

file shows file type.

less allows controlled viewing of large files.

/etc contains system configuration.

/var contains changing system data.

/usr contains installed programs.

symbolic links connect paths.

## philosophy

Linux is not about opening files randomly.

It is about understanding structure: configuration, data, programs, and how the system organizes everything into directories.