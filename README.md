# systems-installs

Installs linux system configuration to production servers after every merge to master.
System configuration is limited to what is common for all servers (applications are
not deployed).

## Items that are insalled

- admin users (grants server access)
- security configurations
- OS level details, like security, common logging configs, unattended upgrades, etc..

## Testing locally

Launch a local vagrant server (a VM), use this as a target for the server setup deployment code.

```
cd ./vagrant/
vagrant up
./run_ansible --env vagrant`
```

Validate installation:
```
vagrant ssh
```
