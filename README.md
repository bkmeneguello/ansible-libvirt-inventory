# Ansible Libvirt Inventory Plugin

## About

Libvirt inventory plugin.


### Requirements

Installed python-libvirt and, preferentially, qemu-guest-agent on each guest.

### Features

## Instructions

Clone this repository into "inventory_plugins" dir relative to your playbook:

```sh
git clone https://github.com/bkmeneguello/ansible-libvirt-inventory.git inventory_plugins/libvirt
```

Add some configurations to your "ansible.cfg":

```
[defaults]
inventory_plugins=./inventory_plugins

[inventory]
enable_plugins = libvirt
```

Create an inventory file with "libvirt.yml" suffix:

```yaml
plugin: libvirt
# check the example inventory for more options
```

Let's test it:

```sh
ansible-inventory -i inventory.libvirt.yml --list
```

If you get a list with all the VM in your host, everything is ok.

You can include the dynamic inventory in your Ansible commands:

```sh
# Ping: connect to all VMs using root user
ansible -i inventory.libvirt.yml all -m ping -u root
```
