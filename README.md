Ansible Role: ganto.gentoo-portage
==================================

Setup Gentoo [Portage configuration](https://wiki.gentoo.org/wiki/Portage#Configuration) such as sync URL or USE flags. It can be used to customize Gentoo stage3 installations as found in e.g. LXC/LXD container images.

Requirements
------------

This role must run against a Gentoo Linux with a minimally working portage setup.

Role Variables
--------------

| Variable Name                            | Description                                                  |
| ---------------------------------------- | ------------------------------------------------------------ |
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
         - name: ganto.gentoo-portage

License
-------

[GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)


Author Information
------------------

The `ganto.gentoo-portage` role was written by Reto Gantenbein | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)