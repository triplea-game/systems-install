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

### Install Vagrant (on time)

Install Vagrant from [vagrant download site](https://www.vagrantup.com/downloads.html)

*Note*, you may need to do some chowning to be able to run virtualbox as non-root:

```bash
sudo chown $USER:$USER -R ~/.vagrant.d/
sudo chown $USER:$USER -R ~/triplea/infrastructure/.vagrant/
```

### Launch Vagrant

```
cd ./vagrant/
vagrant up
```

Stop and/or start from scratch with:
```
cd ./vagrant/
vagrant halt
vagrant destroy
```

### Run Deployment & Validate
```
./run_ansible --env vagrant`
```

Validate installation:
```
cd ./vagrant/
vagrant ssh
```

### Troubleshooting: VM Won't Start

- Open VirtualBox, the VM should be listed there and you can open a console to
  the VM from VirtualBox which will show you the latest console output from
  the VM. This console output may give an indication of what is happening
- Sometimes bringing the VM down and recreating it is the way to go:

