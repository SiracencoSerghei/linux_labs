# Linux Command Line Notes (Part I - Chapter 7:[ Expansion](https://linuxcommand.org/lc3_lts0080.php))

This chapter focuses on how the shell transforms input before executing any command.

Expansion is one of the most important concepts in Linux because it explains why commands sometimes behave differently than expected.

The shell does not pass raw text to programs. It first expands, interprets, and rewrites it.

---

## pathname expansion

The shell replaces patterns with matching filenames.

### wildcard *

Example:
echo *

Result:
all files and directories in the current location

The shell expands * into a list of names before echo runs.

---

### wildcard ?

Matches a single character.

Example:
ls file?.txt

Matches:
file1.txt
fileA.txt

Does not match:
file10.txt

---

### character ranges

Square brackets define sets or ranges.

Examples:
ls file[123].txt
ls file[a-c].txt

This matches specific characters or ranges.

---

## tilde expansion

~ expands to the home directory.

Example:
cd ~

Equivalent to:
cd /home/user

Also:
echo ~

---

## variable expansion

Variables are replaced with their values.

Example:
echo $HOME

Output:
/home/user

Common variables:
HOME  → user home directory
PATH  → command search paths
USER  → current user

---

## command substitution

Command output is inserted into another command.

Example:
echo $(date)

The shell runs date first, then replaces it with its output.

Old style:
echo `date`

---

## arithmetic expansion

The shell can evaluate math expressions.

Example:
echo $((2 + 3 * 4))

Output:
14

Supports basic arithmetic operations.

---

## brace expansion

Generates multiple strings from patterns.

Example:
echo file{1,2,3}.txt

Output:
file1.txt file2.txt file3.txt

Range example:
echo file{1..5}.txt

Output:
file1.txt file2.txt file3.txt file4.txt file5.txt

---

## order of expansion

The shell applies expansions in a specific order:

1. brace expansion
2. tilde expansion
3. parameter (variable) expansion
4. command substitution
5. arithmetic expansion
6. pathname expansion

This order explains why results may differ depending on structure.

---

## quoting vs expansion

Single quotes prevent all expansion:
echo '*'

Double quotes allow some expansion:
echo "$HOME"

No quotes allows full expansion:
echo *

---

## common mistakes

- Expecting * to be passed literally
- Forgetting that variables expand before execution
- Mixing quotes and expecting no transformation

The shell always processes input before programs see it.

---

## summary

Expansion is how the shell transforms input before execution.

Types of expansion:
- pathname expansion (*, ?)
- tilde expansion (~)
- variable expansion ($VAR)
- command substitution $(...)
- arithmetic expansion $((...))
- brace expansion {1..5}

---

## philosophy

You are not interacting with programs directly.

You are writing expressions that the shell rewrites before execution.

Understanding expansion is the difference between guessing and controlling the terminal.