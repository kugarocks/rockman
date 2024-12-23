# Intro

List directory contents.

```bash {copyable}
ls
```

---

## Long Format

With Human Readable Size.

```bash {copyable}
ls -lh
```

---

## Only Dotfiles

```bash {copyable}
ls -ld .*
```

---

## Only Directories

```bash {copyable}
ls -ld */
```

Include hidden directories.

```bash {copyable}
ls -ld .*/ */
```

---

## Specific Directory

```bash {copyable}
ls -ld /usr
```

---

## Show Inode Number

```bash {copyable}
ls -i foo.txt
```
