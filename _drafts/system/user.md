
### change group

FreeBSD

```bash
pw group mod group_name -m user_name
```

## Default shell (login shell)

- FreeBSD/macOS

```bash
chpass -s /usr/loca/bin/bash $user
```

- Linux -> PowerShell

```bash
usermod -s /usr/bin/powershell $user
```

## CLI: Linux vs BSD

No.|Function|Linux|BSD|Comments
---|--------|-----|-------|--------
1|add/del user(s)|useradd<br/>userdel|adduser<br/>(?)|what about macOS?
1|change user info|usermod|chpass|
1|ls with color|ls --color|export CLICOLOR=1|

