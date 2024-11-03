# Intro

Concatenate files and print on the standard output

```bash
cat file
```

---

## Show Line Numbers

```bash
cat -n file
```

---

## Create Multiline File

Without quotes, $HOME will be expanded.

```bash
cat <<EOF > file
line1
$HOME
EOF
```

With quotes(single or double), $HOME will not be expanded.

```bash
cat <<'EOF' > file
line1
$HOME
EOF
```
