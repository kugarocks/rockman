# Intro

Determine if a command is built-in, external, or a function

```bash {copyable}
type [options] command
```

---

## Examples

```bash {copyable}
type cd
```

```txt {title="Output"}
cd is a shell builtin.
```

```bash {copyable}
type useradd
```

```txt {title="Output"}
useradd is /usr/sbin/useradd.
```

---

## Show All Implementations

```bash {copyable}
type -a echo
```

```txt {title="Output"}
echo is a shell builtin
echo is /usr/bin/echo
echo is /bin/echo
```
