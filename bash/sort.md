# Intro

Sort lines of text files.

```bash
sort
```

---

## Reverse Order

```bash
sort -r file
```

---

## Numeric Sort

```bash
sort -n file
```

---

## Sort By Month

Month format: `Jan`, `Feb`, `Mar`.

```bash
sort -M file
```

---

## Specify Column

Default is separated by (consecutive) spaces or tabs.

```bash
sort -k 1 file
```

---

## Specify Delimiter And Column

- `-k` index starts from 1.
- The 3rd column is the user ID.

```bash
sort -t ':' -k 3 -n /etc/passwd
```

---

## Ignore Case

```bash
sort -f file
```

---

## Remove Duplicates

```bash
sort -u file
```
