Ansible Role: ganto.gentoo_portage
==================================

**Ansible Galaxy:** [![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-gentoo__portage-blue.svg?style=popout-square)](https://galaxy.ansible.com/ganto/gentoo_portage)

Setup Gentoo [Portage configuration](https://wiki.gentoo.org/wiki/Portage#Configuration) such as sync URL or USE flags. It can be used to customize Gentoo stage3 installations as found in e.g. LXC/LXD container images.

Requirements
------------

This role must run against a Gentoo Linux with a minimally working portage setup.

Role Variables
--------------

| Variable Name                            | Description                                                  |
| ---------------------------------------- | ------------------------------------------------------------ |
| `gentoo_portage__accept_keywords`        | Set ACCEPT_KEYWORDS variable in `/etc/portage/make.conf`     |
| `gentoo_portage__makeopts`               | Set MAKEOPTS variable in `/etc/portage/make.conf`            |
| `gentoo_portage__makeconf_vars`          | Custom variable definitions for `/etc/portage/make.conf`     |
| `gentoo_portage__profile`                | Set Gentoo profile                                           |
| `gentoo_portage__sync_uri`               | Portage repository synchronization URL                       |
| `gentoo_portage__sync_type`              | Portage synchronization type (e.g. `git`, `rsync`)           |
| `gentoo_portage__sync`                   | Synchronize portage repository after configuration update    |
| `gentoo_portage__sync_force`             | Force portage repository sync during role execution          |
| `gentoo_portage__global_use_enable`      | List of global USE flags to be enabled                       |
| `gentoo_portage__global_use_disable`     | List of global USE flags to be disabled                      |
| `gentoo_portage__packages_default`       | List of default packages to be installed                     |
| `gentoo_portage__packages`               | List of user-defined packages to be installed                |
| `gentoo_portage__packages_clean_sources` | Delete downloaded package source archives after installation |

For the default values of these variables check the `defaults/main.yml`.


Example Playbook
----------------

For a minimal setup simply include the role. The default configuration should be non-destructive to an existing Gentoo installation:

    - hosts: all
      roles:
         - name: ganto.gentoo_portage

License
-------

[GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)


Author Information
------------------

The `ganto.gentoo_portage` role was written by Reto Gantenbein | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)
