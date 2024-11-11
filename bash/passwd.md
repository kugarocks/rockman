# Intro

Change user password.

---

## Modify Current User PWD

Without parameters, it is to change the password of the current user.

```bash {copyable}
passwd
```

---

## Modify User PWD

```bash {copyable}
passwd kuga
```

---

## Disable PWD Login

It will not disable SSH Authentication.

```bash {copyable}
passwd -l kuga
```

The pwd field in the `/etc/shadow` file will be prefixed with `!`.

```bash {copyable}
grep kuga /etc/shadow
```

---

## Enable PWD Login

```bash {copyable}
passwd -u kuga
```
