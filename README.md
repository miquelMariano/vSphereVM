Role Name
=========

vSphereVM is a role to help an vSphere administrators to manage your virtual machines

Requirements
------------

[pyvmomi](https://pypi.python.org/pypi/pyvmomi/) is required

To install:

```shell
$ pip install --upgrade pyvmomi
```

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

```yaml
- hosts: ansible
  user: root
  tasks:
     - name: Ensure that role are up to date
       command: ansible-galaxy install --force {{ item }}
       with_items:
          - miquelMariano.vSphereVM
       when:
          - update_mode | default(False)
       tags: update
       ignore_errors: yes

- hosts: ansible
  user: root
  roles:
     - role: miquelMariano.vSphereVM
```

Execute playbook
----------------

```yaml
ansible-playbook playbooks/vSphereVM.yml -i inventory/servers --e "update_mode=true" --tags=update
```

License
-------

BSD

Author Information
------------------

[@miquelMariano](https://twitter.com/miquelMariano)
