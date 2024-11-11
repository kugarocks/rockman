# Intro

Report file system disk space usage.

```bash {copyable}
df
```

---

## Readable Format

```bash {copyable}
df -h
```

---

## Free Inodes Statistic

```bash {copyable}
df -ih
```

---

## Specify File System

`ext4` is the file system type of Linux.

```bash {copyable}
df -h -t ext4
```

`apfs` is the file system type of macOS.

```bash {copyable}
df -h -t apfs
```
