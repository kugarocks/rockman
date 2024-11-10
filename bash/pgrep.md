# Intro

Look up for processes based on name and other attributes.

---

## Ignore Case

```bash
pgrep -i BASH
```

---

## Specify User Processes

```bash
pgrep -u kuga
```

---

## Process IDs and Names

It will display the process ID and name.

```bash
pgrep -l bash
```

```bash
42977 bash
44150 bash
```

---

## Number of Matching Processes

```bash
pgrep -c bash
```

---

## Specify Parent PID

Get the child processes of the specified parent PID.

```bash
pgrep -P 1729
```

```bash
42912
44084
```

---

## Recently Started Processes

```bash
pgrep -n -l
```

```bash
pgrep -n bash -l
```

---

## Earliest Started Processes

```bash
pgrep -o -l
```

```bash
1 systemd
```

---

## Precision Process Name

```bash
pgrep -x sshd
```
