# Intro

User group file is `/etc/group`.

---

## Display User Group

```bash
id kuga
```

```txt
uid=1000(kuga) gid=1000(kuga) groups=1000(kuga)
```

---

## New Group

```bash
groupadd name
```

---

## Modify Group Name

```bash
groupmod -n newname name
```

---

## Grant User Group

Append the group to the user.

```bash
usermod -aG groupname user
```

Overwrite the user's group.

```bash
usermod -G groupname user
```

---

## Delete User Group

```bash
gpasswd -d user groupname
```

---

## Delete Group

```bash
groupdel name
```
