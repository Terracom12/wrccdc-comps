SSH is a secure[^1] remote shell access program.
Read `man ssh.1` for more info.

## Quick Reference

Log on to a remote host
```bash
# <user>     the REMOTE user account
# <hostname> hostname or ip address
# [port]     optional custom port number (default 22)
ssh <user>@<hostname> [-p <port>]
```
```bash
ssh admin@10.100.23.2
```

Copy your keys to a host (streamlines and secures logon)
May require a package to be downloaded for the commands
```bash
# Only run this if you have not generated a key before
# or if you know what you're doing :D
ssh-keygen  # follow the defaults
```
```bash
# Similar syntax to ssh(1)
ssh-copy-id <user>@<hostname>
# Manual method:
# You may need to mkdir .ssh on the remote system
# MAKE SURE YOU'RE COPYING the .pub key!!!
scp ~/.ssh/id_*****.pub '<user>@<hostname>:~/.ssh'
```


## Notes

Most (all?) of the linux competition servers have been using OpenSSH, which is pretty simple to [configure](https://man.openbsd.org/sshd_config).
Alpine might have been using Dropbear (?)
Not sure how to configure ssh on Windows. Probably doable through the AD interface.


[^1]: Unfortunately, as with anything, it's only as secure as it's configured to be
