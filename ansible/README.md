To set up a vault, run:

```shell
ansible-vault encrypt_string 'ADMIN_PASS_HERE' --name 'vault_admin_password' > <vault-file>.yml
```

Or, just use the paste the generated output directly into an ansible playbook

## Requirements

```
ansible-core
python3-winrm
```


ansible collections

```
ansible.posix
```
