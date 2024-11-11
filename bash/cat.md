# Intro

Concatenate files and print on the standard output.

```bash {copyable}
cat foo.txt
```

---

## Show Line Numbers

```bash {copyable}
cat -n foo.txt
```

Without blank lines:

```bash {copyable}
cat -b foo.txt
```

---

## Display All Characters

```bash {copyable}
cat -A foo.txt
```

`-A` is equivalent to using `-vET` (three cat options combined):

- `-v`: Shows non-printing characters, except for tabs and newlines.
- `-E`: Marks the end of each line with a `$` symbol.
- `-T`: Displays tabs as `^I`.

---

## Create Multiline File

Without quotes, $HOME will be expanded.

```bash {copyable}
cat <<EOF > foo.txt
line1
$HOME
EOF
```

With quotes(single or double), $HOME will not be expanded.

```bash {copyable}
cat <<'EOF' > foo.txt
line1
$HOME
EOF
```
