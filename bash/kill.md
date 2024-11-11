# Intro

Terminate or signal a process.

## Available Signals

```bash {copyable}
kill -l
```

```txt {title="Output"}
 1) SIGHUP    2) SIGINT    3) SIGQUIT   4) SIGILL    5) SIGTRAP
 6) SIGABRT   7) SIGBUS    8) SIGFPE    9) SIGKILL  10) SIGUSR1
11) SIGSEGV  12) SIGUSR2  13) SIGPIPE  14) SIGALRM  15) SIGTERM
......
```

---

## List Signal Name

```bash {copyable}
kill -l 9 15
```

```txt {title="Output"}
KILL
TERM
```

---

### Specify Signal Type

```bash {copyable}
kill -s SIGKILL <PID>
```

```bash {copyable}
kill -9 <PID>
```

---

### Multiple Processes

```bash {copyable}
kill -15 <PID> <PID> <PID>
```
