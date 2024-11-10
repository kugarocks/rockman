# Intro

Print resolved symbolic links or canonical file names.

```bash
readlink /bin
```

`/bin` is a symbolic link to `/usr/bin`.

---

## Final Link

```bash
readlink -f /bin/vim
```

Final link is `/usr/bin/vim.basic`.
