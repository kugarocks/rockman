# Intro

A Stream Text Processor, authored by Lee E. McMahon.

```bash {copyable}
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

## Replace First Occurrence

Replace the first occurrence of 'a' with 'b'.

```bash {copyable}
echo 'aba' | sed 's/a/b/'
```

```bash {title="Output"}
bba
```

---

## Replace Nth Occurrence

Replace the Nth occurrence of 'a' with 'b'.

```bash {copyable}
echo 'aba' | sed 's/a/b/2'
```

```bash {title="Output"}
abb
```

---

## Replace All Occurrences

```bash {copyable}
echo 'aba' | sed 's/a/b/g'
```

```bash {title="Output"}
bbb
```

---

## Execute Mult Commands

Can use `;` to separate, or use the `-e` option.

```bash {copyable}
echo 'aba' | sed 's/a/b/; s/a/c/'
```

```bash {copyable}
echo 'aba' | sed -e 's/a/b/' -e 's/a/c/'
```

```bash {title="Output"}
bbc
```

---

## Using Command File

The `cmd.sed` file content is as follows.

```bash {copyable}
s/a/b/
s/a/c/
```

```bash {copyable}
echo 'aba' | sed -f cmd.sed
```

```bash {title="Output"}
bbc
```

---

## Print Only Replaced Lines

`-n` indicates suppressing output, `p` indicates only outputting matched lines.

```bash {copyable}
echo '
aa bb
cc dd
' | sed -n 's/aa/bb/p'
```

```bash {title="Output"}
bb bb
```

---

## Write Result to File

```bash {copyable}
echo '
aa bb
cc dd
' | sed 's/aa/bb/w out.txt'
```

```bash {copyable}
cat out.txt
```

```bash {title="Output"}
bb bb
```

---

## Modify Delimiter

Can use another symbol to replace the command delimiter `/`.

```bash {copyable}
echo '/bin/sh' | sed 's#/sh#/bash#'
```

```bash {title="Output"}
/bin/bash
```

---

## Specify Line Match

Match the 2nd line.

```bash {copyable}
sed '2s/aa/bb/'
```

Match lines 2-4.

```bash {copyable}
sed '2,4s/aa/bb/'
```

Match lines 2 to the last.

```bash {copyable}
sed '2,$s/aa/bb/'
```

---

## Specify Command Group

```bash {copyable}
sed '2{s/cc/aa/; s/dd/bb/}'
```

```bash {copyable}
sed '2,4{
s/cc/aa/
s/dd/bb/
}'
```

---

## Delete All Lines

```bash {copyable}
sed 'd'
```

---

## Delete Specific Lines

```bash {copyable}
sed '1d'
```

```bash {copyable}
sed '2,4d'
```

```bash {copyable}
sed '2,$d'
```

---

## Delete Matched Lines

```bash {copyable}
sed '/aa bb/d'
```

---

## Insert a Line Before

```bash {copyable}
echo "hello" | sed 'i\New Line'
```

---

## Insert a Line After

```bash {copyable}
echo "hello" | sed 'a\New Line'
```

---

## Specify Line Insert

```bash {copyable}
sed '3i\New Line'
```

---

## Matched Line Insert

```bash {copyable}
sed '/cc/i\New Line'
```

---

## Insert Multiple Lines

Must use `\`.

```bash {copyable}
sed '2i\
New Line 1\
New Line 2
'
```

---

## Modify Line

```bash {copyable}
sed '2c\
Change Line 1\
Change Line 2
'
```

```bash {copyable}
sed '/aa/c\
Change Line 1
'
```

---

## Single Char Replace

```bash {copyable}
echo 'aabbcc' | sed 'y/ac/ca/'
```

```txt {title="Output"}
ccbbaa
```

---

## Print Specific Lines

```bash {copyable}
sed -n '2,5p'
```

---

## Print Before/After Replacement

```bash {copyable}
sed -n '/aa/{p; s/aa/cc/p}'
```

---

## Print Line Number

```bash {copyable}
sed -n '/bb/{=; p}'
```

---

## Reading from File

Create foo and bar files.

```bash {copyable}
echo -e 'aa\nbb' > foo
echo -e '11\n22' > bar
```

Read from the foo file and insert after the first line of bar.

```bash {copyable}
sed '1r foo' bar
```

```txt {title="Output"}
11
aa
bb
22
```

Match string then insert.

```bash {copyable}
sed '/22/r foo' bar
```

```txt {title="Output"}
11
22
aa
bb
```

Match string, insert, and use `d` to delete the matched line.

```bash {copyable}
sed '/22/{
r foo
d
}' bar
```

```txt {title="Output"}
11
aa
bb
```

The following will report a syntax error.

```bash {copyable}
# Will error
sed '/22/{r foo; d}' bar
```

It's not impossible to do it in one line.

```bash {copyable}
sed '/22/r foo' bar | sed '/22/d'
```
