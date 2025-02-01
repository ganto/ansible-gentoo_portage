# Ansible Role: ganto.gentoo_portage

[![CI](https://github.com/ganto/ansible-gentoo_portage/workflows/CI/badge.svg?event=push)](https://github.com/ganto/ansible-gentoo_portage/actions?query=workflow%3ACI)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-gentoo__portage-blue.svg?style=popout-square)](https://galaxy.ansible.com/ganto/gentoo_portage)

Setup Gentoo [Portage configuration](https://wiki.gentoo.org/wiki/Portage#Configuration) such as sync URL or USE flags. It can be used to customize Gentoo stage3 installations as found in e.g. LXC/LXD container images.


## Requirements

This role must run against a Gentoo Linux with a minimally working portage setup.


## Getting Started

For the default values of these variables check the [defaults/main.yml](defaults/main.yml).


## Example Playbook

For a minimal setup simply include the role. The default configuration should be non-destructive to an existing Gentoo installation:

```yaml
- hosts: all
  roles:
    - name: ganto.gentoo_portage
```

## Development

### Testing

There is a [Molecule](https://molecule.readthedocs.io/) test profile that can be used to verify the basic functionality of the role. The default scenario is using the [podman](https://podman.io/) container driver. If you prefer [docker](https://www.docker.com/) you can select the corresponding scenario with the `-s docker` molecule arguments.

1. Ensure you have the necessary dependencies installed (e.g. in a Python [venv](https://docs.python.org/3/tutorial/venv.html)):
```
pip3 install -r molecule/podman/requirements.txt        # for podman
# or
pip3 install -r molecule/docker/requirements.txt        # for docker
```
2. Run the test suite. When using docker, then you need to add the `-s docker` option. The other options in brackets are optional but useful if you need to troubleshoot issues:
```
molecule [-vvv] test [--destroy never][-s docker]
```
3. If you used `--destroy never` the container will remain after the test run and can be inspected interactively via:
```
podman exec -it <container-id> /bin/sh                  # for podman
# or
docker exec -it <container-id> /bin/sh                  # for docker
```
4. Once you're done with inspecting the instanc eit has to be deleted before a new test run can be started:
```
molecule destroy [-s docker]
```


## License

[LGPLv3](https://spdx.org/licenses/LGPL-3.0-or-later.html)


## Author Information

[Changelog](CHANGELOG.md)

The [ganto.gentoo_portage](https://galaxy.ansible.com/ganto/gentoo_portage) role was written and is maintained by:
- [Reto Gantenbein](https://linuxmonk.ch/) | [e-mail](mailto:reto.gantenbein@linuxmonk.ch) | [GitHub](https://github.com/ganto)
