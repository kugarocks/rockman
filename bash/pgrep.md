# Intro

Look up for processes based on name and other attributes.

---

## Ignore Case

```bash {copyable}
pgrep -i BASH
```

---

## Specify User Processes

```bash {copyable}
pgrep -u kuga
```

---

## Process IDs and Names

It will display the process ID and name.

```bash {copyable}
pgrep -l bash
```

```bash {title="Output"}
42977 bash
44150 bash
```

---

## Number of Matching Processes

```bash {copyable}
pgrep -c bash
```

---

## Specify Parent PID

Get the child processes of the specified parent PID.

```bash {copyable}
pgrep -P 1729
```

```bash {title="Output"}
42912
44084
```

---

## Recently Started Processes

```bash {copyable}
pgrep -n -l
```

```bash {copyable}
pgrep -n bash -l
```

---

## Earliest Started Processes

```bash {copyable}
pgrep -o -l
```

```bash {title="Output"}
1 systemd
```

---

## Precision Process Name

```bash {copyable}
pgrep -x sshd
```
