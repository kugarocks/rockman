# Intro

User group file is `/etc/group`.

---

## Display User Group

```bash {copyable}
id kuga
```

```txt
uid=1000(kuga) gid=1000(kuga) groups=1000(kuga)
```

---

## New Group

```bash {copyable}
groupadd name
```

---

## Modify Group Name

```bash {copyable}
groupmod -n newname name
```

---

## Grant User Group

Append the group to the user.

```bash {copyable}
usermod -aG groupname user
```

Overwrite the user's group.

```bash {copyable}
usermod -G groupname user
```

---

## Delete User Group

```bash {copyable}
gpasswd -d user groupname
```

---

## Delete Group

```bash {copyable}
groupdel name
```
