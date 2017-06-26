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

Variables required to connect to vCenter is defined on vars/main.yml:

```yaml
vc_hostname: 192.168.6.10
vc_username: administrator@vsphere.local
vc_password: Secret123!
```

For security reasons is recomended encrypt this file with [ansible-vault](https://miquelmariano.github.io/2017/06/ansible-vault/)

Variables for each VMs to deploy, is defined in the end of file deploy-customize-win.yml

Dependencies
------------

No dependencies

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
