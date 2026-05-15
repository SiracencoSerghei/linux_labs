# Linux Command Line Notes (Part I - Chapter 2: Navigation)

This document covers basic Linux navigation commands from early command line practice.

The goal is to understand how to move inside the filesystem and inspect directories.

## pwd

pwd prints the current working directory.

Example:
pwd

Output shows the full path of your current location in the filesystem.

This is your "where am I" command.

## ls

ls lists files and directories in the current location.

Example:
ls

Common options:
ls -l   (long format, detailed view)
ls -a   (shows hidden files)
ls -h   (human readable sizes, usually with -l)

It helps you see what exists in a directory.

## cd

cd changes the current directory.

Example:
cd /home/user

Go to a specific path.

Examples:
cd ..      (go one level up)
cd ~       (go to home directory)
cd -       (go to previous directory)

This is the main navigation tool in Linux.

## absolute vs relative paths

Absolute path starts from root /:
cd /usr/bin

Relative path depends on current location:
cd Documents

Linux does not care about your intuition, only about paths.

## practical navigation flow

Example workflow:
pwd
ls
cd Documents
ls
cd ..

This is how you move and inspect filesystem step by step.

## hidden files

Files starting with . are hidden.

Example:
ls -a

Hidden files are usually configuration files.

## summary

pwd shows current location.

ls shows contents of directory.

cd changes directory.

Navigation in Linux is path-based, not click-based.

## philosophy

Linux navigation is not about memorizing commands.

It is about understanding the filesystem as a tree and learning how to move through it efficiently.