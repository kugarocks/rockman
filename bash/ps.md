# Intro

Report a snapshot of the current processes.

```bash {copyable}
ps
```

Shows all processes for the current terminal by default.

---

## List All Processes

```bash {copyable}
ps -ef
```

* `-e`: Show all processes.
* `-f`: Show full format.

```bash {copyable}
ps aux
```

* `a`: Show processes for all users.
* `u`: Show user-oriented format.
* `x`: Show processes not attached to a terminal.

---

## List User Processes

```bash {copyable}
ps -fu kuga
```
