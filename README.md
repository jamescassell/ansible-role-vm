vm
==

Create a VM using specified backend.

Requirements
------------

None.  Requirements of relevant backend role applies.

Role Variables
--------------

See `defaults/main.yml`

Dependencies
------------

Depends on a backend role to provision the VM.  Supported roles include:
- `libvirt-vm`
- `openstack-vm`

Example Playbook
----------------

    - name: install a libvirt VM on virthost
      hosts: virtguest
      roles:
      - role: vm
        vm_type: libvirt
        vm_host: virthost
        vm_os_variant: rhel7.6
        vm_cpu_cores: 4
        vm_memory: 4096
        vm_disk_size: 16

    - name: install an OpenStack VM
      hosts: virtguest
      roles:
      - role: vm
        vm_type: openstack
        vm_memory: 4096
        vm_disk_size: 16
        vm_image: cirros

License
-------

Apache-2.0 or MIT or BSD-3-Clause

Author Information
------------------

[James Cassell](https://github.com/jamescassell)
