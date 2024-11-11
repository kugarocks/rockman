# Intro

Modify a user account.

---

## Modify User ID

```bash {copyable}
usermod -u 1001 kuga
```

---

## Modify User Name

```bash {copyable}
usermod -l new old
```

---

## Modify User Shell

`usermod` does not check if the shell exists, use `chsh` instead.

```bash {copyable}
chsh -s /bin/bash kuga
```

---

## Grant User Group

Grant user `kuga` to group `sudo`.

```bash {copyable}
usermod -aG sudo kuga
```

`-a` means append to the existing list of groups.

---

## Disable Login Shell

Set user `kuga`'s shell to `/sbin/nologin`.

```bash {copyable}
usermod -s /sbin/nologin kuga
```

On `/etc/passwd`:

```txt
kuga:x:1000:1000::/home/kuga:/sbin/nologin
```

It will disable all authentication methods.

---

## Enable Login Shell

```bash {copyable}
usermod -s /bin/bash kuga
```

---

## Disable PWD Login

```bash {copyable}
usermod -L kuga
```

The pwd field in the `/etc/shadow` file will be prefixed with `!`.

```bash {copyable}
grep kuga /etc/shadow
```

---

## Enable PWD Login

```bash {copyable}
usermod -U kuga
```
