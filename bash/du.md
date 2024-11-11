# Intro

Estimate file space usage.

```bash {copyable}
du
```

---

## Directory Size

```bash {copyable}
du -sh ~/Downloads
```

---

## Sort Files

Including Subdirectories.

```bash {copyable}
du -ah ~/Downloads/* | sort -rh | head -n 5
```

```bash {copyable}
du -ah ~/Downloads --max-depth=1 | sort -rh | head -n 10
```

Exclude Subdirectories.

```bash {copyable}
du -sh ~/Downloads/* | sort -rh | head -n 5
```
