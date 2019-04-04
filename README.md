SSH-Control
=========

This playbook manages the access of servers through SSH for a particular user

Requirements
------------

This playbook needs no special requirements configured other than ssh access to the servers themselves. 
It works with:

    *  Ubuntu - all
    * Debian - all
    * Redhat - all

Role Variables
--------------

The Play takes the users information including name, group,uid,groups as variables declared in main.yml. For removing  users also same file can be used.
Add the public keys for the user in folder files with name  
```console
{username.pub}
```
Dependencies
------------

This simple playbook uses no extra dependencies.It is recomended that you configure  your command centre ssh-agent with ssh keys, Ansible loads them automatically.

Example Playbook
----------------

Define the users to be manged in the following format.
```yaml
    users:
  - name: jgladwin
    uid: 02301
    is_admin: true
    group: dev
```    
To add a user run the command:
```console
  ansible-playbook -i servers -e "operation=add" ssh-manage.yml
  ```
To remove a user run the command:
```console
 ansible-playbook -i servers -e "operation=remove" ssh-manage.yml
 ```
License
-------

BSD

Author Information
------------------

Johnny Gladwin <johnny.gladwin@outlook.com>
