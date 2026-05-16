# Linux Command Line Notes (Part I - Chapter 4: Manipulating Files and Directories)

This chapter covers basic file and directory manipulation in Linux.

The goal is to learn how to create, copy, move, rename, and remove files directly from the command line.

Linux treats files and directories as objects that can be manipulated with small composable tools.

## mkdir

mkdir creates directories.

Example:
mkdir projects

Create nested directories:
mkdir -p workspace/go/project

The -p option creates parent directories if they do not exist.

## cp

cp copies files and directories.

Examples:
cp file.txt backup.txt
cp file.txt /home/user/Documents

Copy directories recursively:
cp -r source_dir target_dir

Important:
Without -r, directories cannot be copied.

## mv

mv moves or renames files and directories.

Examples:
mv old.txt new.txt
mv file.txt /tmp

Linux uses the same command for moving and renaming.

## rm

rm removes files.

Example:
rm old.txt

Remove directories recursively:
rm -r old_directory

Force remove:
rm -rf dangerous_directory

Important:
Linux usually does not ask for confirmation.
Deleted files are normally gone permanently.

rm -rf is one of the easiest ways to destroy a system if used carelessly.

## touch

touch creates empty files or updates timestamps.

Example:
touch notes.txt

Very common for quick file creation.

## ln

ln creates links between files.

Hard link:
ln file.txt hardlink.txt

Symbolic link:
ln -s file.txt symlink.txt

Symbolic links behave like shortcuts.

## wildcard characters

Linux shell supports pattern matching.

Examples:
*.txt       all txt files
*.go        all Go files
file*       everything starting with "file"

Example:
rm *.tmp

Wildcards are powerful and dangerous if used carelessly.

## practical workflow

Example:
mkdir lab
cd lab
touch notes.txt
cp notes.txt backup.txt
mv backup.txt old_notes.txt
ls
rm old_notes.txt

This is a normal command line workflow for manipulating files.

## summary

mkdir creates directories.

cp copies files and directories.

mv moves and renames files.

rm removes files and directories.

touch creates empty files.

ln creates links.

Wildcards allow pattern matching.

## philosophy

Linux file manipulation is fast because everything is command-driven.

The shell rewards precision and punishes carelessness.