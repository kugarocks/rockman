# Intro

Estimate file space usage.

```bash
du
```

---

## Directory Size

```bash
du -sh ~/Downloads
```

---

## Sort Files

Including Subdirectories.

```bash
du -ah ~/Downloads/* | sort -rh | head -n 5
```

```bash
du -ah ~/Downloads --max-depth=1 | sort -rh | head -n 10
```

Exclude Subdirectories.

```bash
du -sh ~/Downloads/* | sort -rh | head -n 5
```
