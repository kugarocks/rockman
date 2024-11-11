# Intro

Sort lines of text files.

```bash {copyable}
sort
```

---

## Reverse Order

```bash {copyable}
sort -r file
```

---

## Numeric Sort

```bash {copyable}
sort -n file
```

---

## Sort By Month

Month format: `Jan`, `Feb`, `Mar`.

```bash {copyable}
sort -M file
```

---

## Specify Column

Default is separated by (consecutive) spaces or tabs.

```bash {copyable}
sort -k 1 file
```

---

## Specify Delimiter And Column

- `-k` index starts from 1.
- The 3rd column is the user ID.

```bash {copyable}
sort -t ':' -k 3 -n /etc/passwd
```

---

## Ignore Case

```bash {copyable}
sort -f file
```

---

## Remove Duplicates

```bash {copyable}
sort -u file
```
