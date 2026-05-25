# Linux Command Line Notes (Part I - Chapter 7: Seeing the World as the Shell Sees It)

This chapter explains how the shell interprets everything you type before it executes a command.

The shell does not execute raw text. It performs expansions, substitutions, and parsing rules that transform input into final commands.

Understanding this is critical for avoiding unexpected behavior.

## pathname expansion

Pathname expansion (globbing) matches patterns to filenames.

Examples:
*.txt        all text files
file*        files starting with "file"
???.log      files with exactly 3 characters before .log

The shell expands patterns before executing the command.

Example:
ls *.txt

Becomes:
ls file1.txt file2.txt

## tilde expansion

~ expands to the current user's home directory.

Examples:
cd ~
cd ~/Documents

Also:
~user expands to another user's home directory (if allowed).

Example:
cd ~root

## arithmetic expansion

The shell can evaluate arithmetic expressions.

Syntax:
$(( expression ))

Example:
echo $((2 + 3))

Supported operations:
+ - * / % (modulo)

Example:
echo $((10 * 5))

## brace expansion

Brace expansion generates multiple strings.

Examples:
echo file{1,2,3}.txt

Output:
file1.txt file2.txt file3.txt

Ranges:
echo {1..5}

Output:
1 2 3 4 5

Example:
mkdir project{A,B,C}

Creates multiple directories at once.

## parameter expansion

Parameter expansion accesses variables.

Example:
echo $HOME

Common variables:
$USER → current username
$PATH  → directories where commands are searched
$HOME  → user home directory

Default value syntax:
${VAR:-default}

Example:
echo ${NAME:-unknown}

## command substitution

Command output can be used inside another command.
Command substitution uses output of a command as input.

Syntax:
$(command)

Example:
echo $(date)

Older syntax:
`command`

Example:
echo `whoami`

Command is executed first, then replaced with its output.

## quoting rules

Quoting controls how the shell interprets special characters.

### double quotes ""

Preserve most characters but allow expansions.

Example:
echo "$HOME"

Output expands HOME variable.

### single quotes ''

Preserve everything literally.

Example:
echo '$HOME'

Output:
$HOME

No expansion happens.

## escaping characters

Escaping removes special meaning from characters.

Example:
echo \$HOME

Output:
$HOME

Backslash tells shell to treat next character literally.

## backslashes

Backslash is used for:

- escaping special characters
- breaking long lines

Example:
echo "hello \
world"

Output:
hello world

## summary

The shell transforms input before execution using:

- pathname expansion (globbing)
- tilde expansion (~)
- arithmetic expansion ($(( )))
- brace expansion ({ })
- parameter expansion ($VAR)
- command substitution ($( ))
- quoting (" ", ' ')
- escaping (\)

## philosophy

What you type is not what runs.

The shell rewrites your input first, then executes the result.

Understanding this prevents confusion and unpredictable command behavior.