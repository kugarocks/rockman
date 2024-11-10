# Intro

Change user password.

---

## Modify Current User PWD

Without parameters, it is to change the password of the current user.

```bash
passwd
```

---

## Modify User PWD

```bash
passwd kuga
```

---

## Disable PWD Login

It will not disable SSH Authentication.

```bash
passwd -l kuga
```

The pwd field in the `/etc/shadow` file will be prefixed with `!`.

```bash
grep kuga /etc/shadow
```

---

## Enable PWD Login

```bash
passwd -u kuga
```
