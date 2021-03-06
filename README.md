# Ansible provisioning

Type just `vagrant up` to spawn a cakephp project
in an ubuntu virtualbox mapping the project directory
onto `/vagrant` at the box.

The app runs at http://192.168.192.168

Roles and tasks included:
 * `nginx`
 * `php5-fpm`
 * `mysql` with `Config/Schema/tables.sql` preloaded
 * build via `composer`, `bower` and `grunt`
 
# Adding to a cakephp project
```
bower install ptica/ansible --save
cp Vendor/ansible/Vagrantfile.default Vagrantfile
mkdir -p Config/ansible/vars/ && cp Vendor/ansible/vars/all.yml Config/ansible/vars/all.yml
vim Vagrantfile # name your box there
```


# TODOs

 * [x] include Vagrantfile.default to copy into fresh project dir
 * [x] include `app/Config/ansiblevars/all.yml` settings from app directory
 * [ ] for win users think about configuring ssh keys for git commits
 * [ ] clear cache during provisioning so there is no right conflict?
 * [ ] bash autocomplete on guest



# Ack
Tasks and roles come from the incredibe http://phansible.com/ project!
