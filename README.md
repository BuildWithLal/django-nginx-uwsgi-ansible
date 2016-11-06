### Deploy Django and Postgres on Nginx and uWSGI
We are using Vagrant and Ansible to deploy Django application on Vagrant box but you can reuse same ansible playbook to deploy on any other Ubuntu server 14.04. We are using Python virtualenv to deploy Django application.


####Enviroment
```
1. Vagrant=1.8
2. Ansible=2.1
3. Ubuntu Server=14.04 trusty
4. Python=2.7
5. Django=1.10
6. Postgresql=9.4
7. Nginx
8. uWSGI
```

####NOTE:
1. Update `Vagrantfile` to change your synced_folders.
```
config.vm.synced_folder "./project", "/home/vagrant/egerin/code/"
```
2. Update `inventory.ini` to replace your server IP or host name instead of `web`
3. Update `shared_vars.main`, `/roles/setup/vars/main.yml`, `/roles/deploy/vars/main.yml` and `/roles/setup/templates` to make your desired changes i.e http port, django settings module, project dir etc


####Using Vagrant
```
# Switch to directory and run command to create machine and run provisions
vagrant up

# run provisions if machine is already created
vagrant provisions

```


####Using Ansible directly
Switch to directory and run command to run provisions on machine listed in inventory.ini
```
ansible-playbook -i inventory.ini site.yml
```
