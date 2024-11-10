# Intro

A Stream Text Processor, authored by Lee E. McMahon.

```bash
sed [OPTIONS] 'command' file
```

- `OPTIONS`: Command options.
- `command`: Print, replace, delete, etc.
- `file`: The file to process; if omitted, reads from STDIN.

Omitting file enters interactive mode, executing one line at a time.

## Execution Process

- Reading a line of data:
  - With a match rule:
    - Match successful: Executes related operations.
    - Match failed: Prints data as is.
  - Without a match rule: Executes related operations.

## Command Quotes

- Single quotes: Reduces the impact of escape characters, preferably used.
- Double quotes: Can use variable parameters, requires handling special characters.

---

### Replace First Occurrence

Replace the first occurrence of 'a' with 'b'.

```bash {frame="none"}
echo 'aba' | sed 's/a/b/'
```

```bash {frame="none"}
bba
```

### Replace Nth Occurrence

Replace the Nth occurrence of 'a' with 'b'.

```bash {frame="none"}
echo 'aba' | sed 's/a/b/2'
```

```bash {frame="none"}
abb
```

### Replace All Occurrences

```bash {frame="none"}
echo 'aba' | sed 's/a/b/g'
```

```bash {frame="none"}
bbb
```

### Execute Mult Commands

Can use `;` to separate, or use the `-e` option.

```bash {frame="none"}
echo 'aba' | sed 's/a/b/; s/a/c/'
```

```bash {frame="none"}
echo 'aba' | sed -e 's/a/b/' -e 's/a/c/'
```

```bash {frame="none"}
bbc
```

### Using Command File

The `cmd.sed` file content is as follows.

```bash {frame="none"}
s/a/b/
s/a/c/
```

```bash {frame="none"}
echo 'aba' | sed -f cmd.sed
```

```bash {frame="none"}
bbc
```

### Print Only Replaced Lines

`-n` indicates suppressing output, `p` indicates only outputting matched lines.

```bash {frame="none"}
echo '
aa bb
cc dd
' | sed -n 's/aa/bb/p'
```

```bash {frame="none"}
bb bb
```

### Write Result to File

```bash {frame="none"}
echo '
aa bb
cc dd
' | sed 's/aa/bb/w out.txt'
```

```bash {frame="none"}
cat out.txt
```

```bash {frame="none"}
bb bb
```

### Modify Delimiter

Can use another symbol to replace the command delimiter `/`.

```bash {frame="none"}
echo '/bin/sh' | sed 's#/sh#/bash#'
```

```bash {frame="none"}
/bin/bash
```

### Specify Line Match

Match the 2nd line.

```bash {frame="none"}
sed '2s/aa/bb/'
```

Match lines 2-4.

```bash {frame="none"}
sed '2,4s/aa/bb/'
```

Match lines 2 to the last.

```bash {frame="none"}
sed '2,$s/aa/bb/'
```

### Specify Command Group

```bash {frame="none"}
sed '2{s/cc/aa/; s/dd/bb/}'
```

```bash {frame="none"}
sed '2,4{
s/cc/aa/
s/dd/bb/
}'
```

### Delete All Lines

```bash {frame="none"}
sed 'd'
```

### Delete Specific Lines

```bash {frame="none"}
sed '1d'
```

```bash {frame="none"}
sed '2,4d'
```

```bash {frame="none"}
sed '2,$d'
```

### Delete Matched Lines

```bash {frame="none"}
sed '/aa bb/d'
```

### Insert a Line Before

```bash {frame="none"}
echo "hello" | sed 'i\New Line'
```

### Insert a Line After

```bash {frame="none"}
echo "hello" | sed 'a\New Line'
```

### Specify Line Insert

```bash {frame="none"}
sed '3i\New Line'
```

### Matched Line Insert

```bash {frame="none"}
sed '/cc/i\New Line'
```

### Insert Multiple Lines

Must use `\`.

```bash {frame="none"}
sed '2i\
New Line 1\
New Line 2
'
```

### Modify Line

```bash {frame="none"}
sed '2c\
Change Line 1\
Change Line 2
'
```

```bash {frame="none"}
sed '/aa/c\
Change Line 1
'
```

### Single Char Replace

```bash {frame="none"}
echo 'aabbcc' | sed 'y/ac/ca/'
```

```txt {frame="none"}
ccbbaa
```

### Print Specific Lines

```bash {frame="none"}
sed -n '2,5p'
```

### Print Before/After Replacement

```bash {frame="none"}
sed -n '/aa/{p; s/aa/cc/p}'
```

### Print Line Number

```bash {frame="none"}
sed -n '/bb/{=; p}'
```

### Reading from File

Create foo and bar files.

```bash {frame="none"}
echo -e 'aa\nbb' > foo
echo -e '11\n22' > bar
```

Read from the foo file and insert after the first line of bar.

```bash {frame="none"}
sed '1r foo' bar
```

```txt {frame="none"}
11
aa
bb
22
```

Match string then insert.

```bash {frame="none"}
sed '/22/r foo' bar
```

```txt {frame="none"}
11
22
aa
bb
```

Match string, insert, and use `d` to delete the matched line.

```bash {frame="none"}
sed '/22/{
r foo
d
}' bar
```

```txt {frame="none"}
11
aa
bb
```

The following will report a syntax error.

```bash {frame="none"}
# Will error
sed '/22/{r foo; d}' bar
```

It's not impossible to do it in one line.

```bash {frame="none"}
sed '/22/r foo' bar | sed '/22/d'
```
