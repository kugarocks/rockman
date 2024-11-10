# Intro

Signal for processes based on name and other attributes.

* The default signal for the `pkill` command is `SIGTERM`.
* Corresponding to number `15`.
* For a graceful termination.

---

## Specify Signal Type

```bash
pkill -SIGKILL bash
```

```bash
pkill -9 bash
```

---

## Specify User Processes

```bash
pkill -u kuga
```

```bash
pkill -9 -u kuga bash
```

---

## Precision Process Name

```bash
pkill -x sshd
```
