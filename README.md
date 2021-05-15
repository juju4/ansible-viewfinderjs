[![Actions Status - Master](https://github.com/juju4/ansible-viewfinderjs/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-viewfinderjs/actions?query=branch%3Amaster)
[![Actions Status - Devel](https://github.com/juju4/ansible-viewfinderjs/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-viewfinderjs/actions?query=branch%3Adevel)

# viewfinderjs ansible role

Install Remote Browser Isolation ViewFinderJS

* https://dosyago.com/
* https://github.com/i5ik/ViewFinderJS

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.10

### Operating systems

Tested on Ubuntu 18.04 and 20.04, Centos 7 and 8.

## Example Playbook

Just include this role in your list.
For example

```
- host: myhost
  roles:
    - juju4.viewfinderjs
```

## Variables

```
viewfinderjs_setup: native
# viewfinderjs_setup: docker
viewfinderjs_git_repo: 'https://github.com/i5ik/ViewFinderJS.git'
viewfinderjs_version: v2.53.0
viewfinderjs_root: /opt/viewfinderjs
```

## Continuous integration

This role has a GitHub action configuration along molecule.

```
$ pip install molecule docker
$ molecule test
$ MOLECULE_DISTRO=ubuntu:20.04 molecule test --destroy=never
```

## Troubleshooting & Known issues

N/A

## License

BSD 2-clause
