# Intro

Change file mode bits.

## Symbolic Mode

`u` represents user: adds execution permission for the user.

```bash {copyable}
chmod u+x file
```

`g` represents group: removes write permission for the group.

```bash {copyable}
chmod g-w file
```

`o` represents others: adds read permission for others.

```bash {copyable}
chmod g+r file
```

`a` represents all: adds execution permission for all.

```bash {copyable}
chmod a+x file
```
