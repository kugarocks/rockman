# Intro

Create a new user or update default new user information.

```bash {copyable}
useradd foo
```

The above command will not create a home directory.

---

## With Home Directory

```bash {copyable}
useradd -m foo
```

---

## Default Configuration

```bash {copyable}
useradd -D
```

```txt {title="Output"}
GROUP=100
HOME=/home
INACTIVE=-1
EXPIRE=
SHELL=/bin/bash
SKEL=/etc/skel
CREATE_MAIL_SPOOL=no
```
