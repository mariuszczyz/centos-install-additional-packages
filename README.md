# CentOS 7 Common Initial Setup Tasks

This role can be used to install additional software packages.

## Requirements

None.

## Role Variables

## Dependencies

Optional roles depending on the repository source of the packages:

mariuszczyz.centos-epel:

Install from `ansible-galaxy install mariuszczyz.centos_epel`

Source: <https://github.com/mariuszczyz/centos-epel>

mariuszczyz.centos-remi:

Install from `ansible-galaxy install mariuszczyz.centos_remi`

Source: <https://github.com/mariuszczyz/centos-remi>

## Example Playbook

Fetch this role from Ansible Galaxy:

`ansible-galaxy install mariuszczyz.centos-install-additional-packages`

In playbook.yml:

```bash
- hosts: servers
  roles:
    - { role: mariuszczyz.centos-install-additional-packages, tags: ['install-additional-packages'] }
```

Before any SSH hardening configuration changes are applied this ansible-playbook command should be ran (as root):

`ansible-playbook -i hosts playbook.yml --user root --ask-pass --limit=hostname`

After SSH hardening configuration changes are made which prohibit root login run ansible-playbook as regular user:

`ansible-playbook -i hosts playbook.yml --user username --become --ask-sudo-pass --limit=hostname`

## License

BSD

## Author Information

Author: Mariusz Czyz  

Date: 09/2018
