# Intro

Print resolved symbolic links or canonical file names.

```bash {copyable}
readlink /bin
```

`/bin` is a symbolic link to `/usr/bin`.

---

## Final Link

```bash {copyable}
readlink -f /bin/vim
```

Final link is `/usr/bin/vim.basic`.
