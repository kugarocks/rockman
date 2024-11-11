# Intro

Global Regular Expression Print.

```bash {copyable}
grep
```

---

## Reverse Matching

```bash {copyable}
grep -v foo file
```

---

## Ignore Case

```bash {copyable}
grep -i Foo file
```

---

## Count Matching Lines

```bash {copyable}
grep -c foo file
```

---

## Fixed String Matching

Without regex.

```bash {copyable}
grep -F foo file
```

---

## Recursive Dir Search

```bash {copyable}
grep -r foo /path
```

---

## Matching File Names

```bash {copyable}
grep -l foo *.txt
```

---

## Non-Matching File Names

```bash {copyable}
grep -rL foo /path
```

---

## With Next N Lines

After:

```bash {copyable}
grep -A 3 foo file
```

---

## With Prev N Lines

Before:

```bash {copyable}
grep -B 3 foo file
```

---

## With Context

```bash {copyable}
grep -C 3 foo file
```

---

## Match Multiple Words

```bash {copyable}
grep -E 'foo|bar' file
```

```bash {copyable}
grep -e 'foo' -e 'bar' file
```

---

## Exclude Files in Dir

```bash {copyable}
grep foo --exclude="*.log" /path
```

---

## Match Files in Dir

```bash {copyable}
grep foo --include="*.txt" /path
```
