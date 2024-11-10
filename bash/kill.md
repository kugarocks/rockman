# Intro

Terminate or signal a process.

## Available Signals

```bash
kill -l
```

```txt
 1) SIGHUP    2) SIGINT    3) SIGQUIT   4) SIGILL    5) SIGTRAP
 6) SIGABRT   7) SIGBUS    8) SIGFPE    9) SIGKILL  10) SIGUSR1
11) SIGSEGV  12) SIGUSR2  13) SIGPIPE  14) SIGALRM  15) SIGTERM
......
```

---

## List Signal Name

```bash
kill -l 9 15
```

* KILL
* TERM

---

### Specify Signal Type

```bash
kill -s SIGKILL <PID>
```

```bash
kill -9 <PID>
```

---

### Multiple Processes

```bash
kill -15 <PID> <PID> <PID>
```
