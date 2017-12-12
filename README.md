# Ansible Role: VMware Management Tools for Windows

This role installs all of the clients for vSphere 5.0 through 6.0 onto a Windows system. It also installs a copy of Chrome for using the web management interfaces (HTML5/Flash).

## Example Using Packer

**Playbook `playbook-vmware-management.yml`**

```
---
- hosts: all
  roles:
    - ansible-role-vmware-management
```

**Packer template**

```
  "provisioners": [
    {
      "type": "ansible",
      "playbook_file": "playbook-vmware-management.yml",
      "extra_arguments": [
          "--connection", "packer",
          "--extra-vars", "ansible_shell_type=powershell ansible_shell_executable=None"
      ]
    }
  ]
```