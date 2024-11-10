# Intro

Determine if a command is built-in, external, or a function

```bash
type [options] command
```

---

## Examples

```bash
type cd
```

`cd` is a shell builtin.

```bash
type useradd
```

`useradd` is `/usr/sbin/useradd`.

---

## Show All Implementations

```bash
type -a echo
```

```txt
echo is a shell builtin
echo is /usr/bin/echo
echo is /bin/echo
```
