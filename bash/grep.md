# Intro

Global Regular Expression Print.

```bash
grep
```

---

## Reverse Matching

```bash
grep -v foo file
```

---

## Ignore Case

```bash
grep -i Foo file
```

---

## Count Matching Lines

```bash
grep -c foo file
```

---

## Fixed String Matching

Without regex.

```bash
grep -F foo file
```

---

## Recursive Dir Search

```bash
grep -r foo /path
```

---

## Matching File Names

```bash
grep -l foo *.txt
```

---

## Non-Matching File Names

```bash
grep -rL foo /path
```

---

## With Next N Lines

After:

```bash
grep -A 3 foo file
```

---

## With Prev N Lines

Before:

```bash
grep -B 3 foo file
```

---

## With Context

```bash
grep -C 3 foo file
```

---

## Match Multiple Words

```bash
grep -E 'foo|bar' file
```

```bash
grep -e 'foo' -e 'bar' file
```

---

## Exclude Files in Dir

```bash
grep foo --exclude="*.log" /path
```

---

## Match Files in Dir

```bash
grep foo --include="*.txt" /path
```
