# Linux Command Line Notes (Part I - Chapter 7: Seeing the World as the Shell Sees It)

This chapter explains how the shell interprets characters, words, paths, and special symbols.

The goal is to understand how Linux “reads” commands differently from humans, and why quoting, expansion, and escaping matter.

The shell is not confused — it is just extremely literal and rules-based.

---

## echo

echo prints text to stdout.

Example:
echo hello

Output:
hello

The shell processes input first, then echo simply prints the result.

---

## expansion

The shell expands special characters before executing commands.

Example:
echo *

The * is not passed to echo directly. The shell expands it into a list of files in the current directory.

This is called pathname expansion.

---

## wildcards

Common wildcards:

*   matches anything
?   matches a single character

Examples:
ls *.txt
ls file?.txt

The shell replaces patterns with matching filenames before execution.

---

## quoting

Quoting controls how the shell interprets special characters.

### single quotes

Strong protection. Everything is literal.

Example:
echo '*'

Output:
*

Nothing is expanded inside single quotes.

---

### double quotes

Weak protection. Most characters are literal, but some expansions still happen.

Example:
echo "$HOME"

Output:
/home/user

Variables still expand inside double quotes.

---

## escaping (\)

Backslash removes special meaning from the next character.

Example:
```
echo \*
```
Output:
*

The shell treats * as a normal character.

---

## variables

Shell variables store values.

Example:
echo $HOME

Common variables:
HOME → user home directory
PATH → directories where commands are searched

---

## PATH

PATH is a list of directories the shell searches for commands.

Example:
echo $PATH

When you type a command, the shell checks each directory in PATH to find an executable.

---

## command substitution

Command output can be used inside another command.

Example:
echo $(date)

The shell runs date first, then replaces it with its output.

---

## arithmetic expansion

The shell can perform math.

Example:
echo $((2 + 3))

Output:
5

---

## seeing how shell processes a command

Example:
echo *.txt

Step-by-step:
1. shell finds *.txt
2. expands it to matching filenames
3. passes expanded list to echo
4. echo prints result

The command never sees the asterisk.

P.S. glob expands only if there are matches. If no files match, the pattern is passed as-is.

---

## common confusion

Why this happens:
echo *

Because shell expands first, not the command.

Why this does NOT work as expected sometimes:
Programs receive processed input, not raw text.

---

## summary

Shell processes everything before execution.

Key concepts:
- expansion replaces patterns with values
- quotes control interpretation
- escape removes special meaning
- variables store data
- PATH defines command lookup
- command substitution inserts output into commands

---

## philosophy

You are not typing commands directly into programs.

You are writing instructions for the shell, and the shell transforms them before anything runs.

Understanding this difference is the key to predictable Linux behavior.