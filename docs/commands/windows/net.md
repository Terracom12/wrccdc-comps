the [net command](https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/net-commands-on-operating-systems) is a versatile utility for managing local and network resources.

## Common Operations

### [`net user`](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/net-user) - list and manage local users
```bat
net user <UserName> {<Password> | *}
net user <UserName> {<Password> | *} /add
net user <UserName> /delete
```


### [`net localgroup`](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc725622(v=ws.11)) - manage local groups

```bat
net localgroup <GroupName> <Name> {/add | /delete}
```

manage `Administrators` and `Remote Desktop Users` user group affiliations

```bat
net localgroup Administrators JohnDoe /add
net localgroup "Remote Desktop Users" AliceLidell /delete
```
