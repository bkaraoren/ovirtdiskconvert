vm_disk_convert
===============
This role is used to convert RHV/oVirt virtual disks from thin to preallocated or preallocated to thin format on the specified virtual machine. It is also possible to free space in the disk image that is not used by its filesystem. As a result, the image will occupy less space on the storage.

Requirements
------------
This role utilizes the [ovirt ansible modules](https://docs.ansible.com/ansible/latest/collections/ovirt/ovirt/index.html) provided by the Ovirt community.

Role Variables
--------------
This role expects a number of variables to be set. See the [defaults/main.yml](defaults/main.yml) file for full explanation.

Dependencies
------------
None

Example Playbook
----------------
Define variables to convert (see defaults/main.yml for more info):

Shared variables
----------------
rhv_create_vms_rhvm: "rhvm host name"

rhv_create_vms_rhvm_user: "username"

rhv_create_vms_rhvm_password: "password"

host: "host"

Execute role in a playbook:

```yaml
- name: RHV VM Virtual Disk Convert
  gather_facts: false
  hosts: rhvm

  tasks:
    - name: Convert virtual disks of the VM on RHV
      import_role:
        name: vm_disk_convert
      tags:
        - vm_disk_convert
```

License
-------
CC-BY-SA-4.0 (https://creativecommons.org/licenses/by-sa/4.0/)

Author Information
------------------
Bilhan Karaoeren

Ali Akkaya
