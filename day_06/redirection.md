# Linux Command Line Notes (Part I - Chapter 6: Redirection)

This chapter explains how Linux handles input and output, and how commands can be combined using redirection and pipes.

The core idea: small tools produce text, and you can redirect, filter, and combine that text to build workflows.

## standard streams

Every Linux program uses three standard streams:

- stdin  (input)
- stdout (normal output)
- stderr (error output)

By default:
- input comes from keyboard
- output goes to terminal

Redirection changes this behavior.

## output redirection (> and >>)

> redirects output to a file (overwrite)

Example:
echo "hello" > file.txt

>> appends output to a file

Example:
echo "more text" >> file.txt

If file does not exist, it is created.

## input redirection (<)

< takes input from a file

Example:
cat < file.txt

Instead of typing input manually, data comes from a file.

## pipes (|)

Pipe connects output of one command to input of another.

Example:
cat file.txt | sort

Pipes allow chaining commands into processing pipelines.

## cat

cat displays file contents or concatenates files.

Example:
cat file.txt

Multiple files:
cat file1.txt file2.txt

Used often as a simple data source for pipelines.

## sort

sort orders lines of text.

Example:
sort file.txt

Sorting is lexical by default.

## uniq

uniq removes duplicate adjacent lines.

Example:
sort file.txt | uniq

Important:
uniq only works properly on sorted input.

## grep

grep searches text using patterns.

Example:
grep "error" file.txt

Useful for filtering logs and large text data.

## rg (ripgrep)

rg is a modern alternative to grep.

Example:
rg "error"

Advantages:
- faster
- better defaults
- recursive search by default

Used in modern development environments.

## wc

wc counts lines, words, and bytes.

Example:
wc file.txt

Common options:
-l   lines
-w   words
-c   bytes

Example:
wc -l file.txt

## head

head shows first lines of a file.

Example:
head file.txt

Default is 10 lines.

Custom:
head -n 5 file.txt

## tail

tail shows last lines of a file.

Example:
tail file.txt

Useful for logs.

Follow mode:
tail -f logfile.log

Shows live updates.

## tee

tee reads input and writes to both output and file.

Example:
echo "data" | tee file.txt

Useful for debugging pipelines.

## combined example

Example pipeline:
cat file.txt | grep "error" | sort | uniq | wc -l

This:
- reads file
- filters lines
- sorts them
- removes duplicates
- counts results

## summary

Redirection controls input and output of commands.

Key tools:
cat → display files
sort → sort lines
uniq → remove duplicates
grep / rg → search text
wc → count text
head → first lines
tail → last lines
tee → split output

## philosophy

Linux is not about individual commands.

It is about combining simple tools into powerful pipelines using redirection and streams.