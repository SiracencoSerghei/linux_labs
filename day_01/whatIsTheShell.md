# Linux Command Line Notes (Part I)

This document contains practical notes from learning Linux command line fundamentals based on "The Linux Command Line (3rd Edition)".

The focus is practical understanding of terminal behavior.

## What is a shell

A shell is a program that provides an interface between the user and the operating system kernel.

You type commands, the shell interprets them, and the kernel executes them.

Common shells are bash, zsh, and fish.

Example:
echo "hello"

Output:
hello

## df

df shows disk space usage on mounted filesystems.

Example:
df -h

-h means human-readable format.

It shows filesystem size, used space, available space, and mount points.

## uptime

uptime shows how long the system has been running and system load averages.

Example:
uptime

It includes current time, uptime duration, number of users, and load averages for 1, 5, and 15 minutes.

## date

date prints the current system date and time.

Example:
date

Used for logs, scripts, and time verification.

## exit

exit closes the current shell session.

It returns to the previous shell or closes the terminal.

## Summary

Shell is a command interpreter.

Linux tools are small and composable.

df shows disk usage.

uptime shows system load and uptime.

date shows system time.

exit ends the session.

## Philosophy

Linux is about understanding how small tools combine into systems, not memorizing commands.