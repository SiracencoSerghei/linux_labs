# Linux Command Line Notes (Part I - Chapter 8: Advanced Keyboard Tricks)

This chapter covers keyboard shortcuts and command line editing techniques used in the Linux shell.

The goal is to reduce repetitive typing and navigate the terminal efficiently without constantly retyping commands.

Most shell productivity comes from editing and reusing commands quickly.

---

## command history

The shell stores previously executed commands.

View history:
history

Reuse previous command:
!!

Run command number from history:
!42

Search history interactively:
Ctrl + R

Example:
Press Ctrl + R and type:
git

The shell searches backward through previous commands matching "git".

Press Ctrl + R repeatedly to continue searching.

---

## cursor movement shortcuts

Move inside the current command line without using arrow keys.

Shortcuts:
Ctrl + A   move to beginning of line
Ctrl + E   move to end of line
Alt + B    move backward one word
Alt + F    move forward one word

Useful for editing long commands quickly.

---

## deleting text

Delete parts of the command line efficiently.

Shortcuts:
Ctrl + U   delete from cursor to beginning
Ctrl + K   delete from cursor to end
Ctrl + W   delete previous word
Alt + D    delete next word

These shortcuts save significant time during terminal work.

---

## clearing the screen

Clear terminal output:
clear

Keyboard shortcut:
Ctrl + L

This does not remove command history. It only clears visible terminal output.

---

## autocomplete with TAB

The shell supports automatic completion.

Example:
cd Doc<TAB>

May expand to:
cd Documents

Double TAB shows possible matches.

Autocomplete reduces typing and prevents mistakes.

---

## history expansion

Reuse parts of previous commands.

Previous argument:
!$

Example:
mkdir project
cd !$

Expands to:
cd project

Previous command:
!!

Useful for repeated operations.

---

## editing previous commands

Use arrow keys:
Up Arrow   previous command
Down Arrow next command

Commands can be modified before execution instead of retyped.

---

## copying and pasting in terminal

Common terminal shortcuts:
Ctrl + Shift + C   copy
Ctrl + Shift + V   paste

Normal Ctrl + C is not copy in terminal.

Ctrl + C sends an interrupt signal to stop running programs.

---

## interrupting processes

Stop running command:
Ctrl + C

Suspend process:
Ctrl + Z

These are process control shortcuts, not text editing shortcuts.

---

## practical workflow

Example:
1. run long command
2. Up Arrow to reuse it
3. Ctrl + A to move to start
4. edit command
5. TAB for autocomplete
6. Enter to execute

This is normal terminal productivity workflow.

---

## summary

Key concepts:
- history stores commands
- Ctrl + R searches history
- keyboard shortcuts edit command lines quickly
- TAB provides autocomplete
- Ctrl + C interrupts processes
- command reuse is faster than retyping

---

## philosophy

Efficient terminal usage is not about typing faster.

It is about minimizing unnecessary typing and learning how to manipulate commands intelligently.