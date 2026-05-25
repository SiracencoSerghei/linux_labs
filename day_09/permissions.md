# Linux Command Line Notes (Part I - Chapter 9: Permissions)

This chapter explains how Linux controls access to files and directories using permissions.

Linux is not trusting. Every file has rules about who can read, write, or execute it.

## ownership

Every file has two owners:

- user (owner)
- group

And one universal category:

- others (everyone else)

Check ownership:
ls -l

Example output:
-rw-r--r-- 1 user user  file.txt

## permission structure

Permissions are shown as 10 characters:

-rw-r--r--

Breakdown:

- first character: file type
- next 3: user permissions
- next 3: group permissions
- last 3: others permissions

## permission types

Each group has 3 possible permissions:

r → read
w → write
x → execute

Example:
rw- = read + write
r-x = read + execute
r-- = read only

## chmod

chmod changes file permissions.

Symbolic mode:

Example:
chmod u+x script.sh

Meaning:
- u → user
- g → group
- o → others
- a → all

Add or remove permissions:
+ add
- remove

Examples:
chmod g-w file.txt
chmod o+r file.txt

Numeric mode:

r = 4
w = 2
x = 1

Example:
chmod 755 script.sh

Breakdown:
7 (user) = rwx
5 (group) = r-x
5 (others) = r-x

## chown

chown changes file owner.

Example:
chown user file.txt

Change owner and group:
chown user:group file.txt

## chgrp

chgrp changes group ownership.

Example:
chgrp developers file.txt

## umask

umask controls default permissions for new files.

Example:
umask 022

This subtracts permissions from defaults:
- files
- directories

Default:
files usually 666
directories usually 777

## executable files

A file is executable only if it has x permission.

Example:
chmod +x script.sh

Then it can be run:
./script.sh

## directories and permissions

For directories:

r → list contents
w → create/delete files
x → enter directory (cd)

Without x, directory is inaccessible even if readable.

## practical example

mkdir test
cd test
touch file.txt
chmod 600 file.txt

Now:
- only owner can read/write
- others have no access

## summary

Linux permissions control access through:

- user, group, others
- read, write, execute
- chmod for permissions
- chown for ownership
- chgrp for group changes
- umask for defaults

## philosophy

Linux assumes multi-user environment.

Permissions are not optional — they define system security at the filesystem level.