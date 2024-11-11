# Intro

Signal for processes based on name and other attributes.

* The default signal for the `pkill` command is `SIGTERM`.
* Corresponding to number `15`.
* For a graceful termination.

---

## Specify Signal Type

```bash {copyable}
pkill -SIGKILL bash
```

```bash {copyable}
pkill -9 bash
```

---

## Specify User Processes

```bash {copyable}
pkill -u kuga
```

```bash {copyable}
pkill -9 -u kuga bash
```

---

## Precision Process Name

```bash {copyable}
pkill -x sshd
```
