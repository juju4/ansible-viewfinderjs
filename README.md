[![Actions Status - Master](https://github.com/juju4/ansible-viewfinderjs/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-viewfinderjs/actions?query=branch%3Amaster)
[![Actions Status - Devel](https://github.com/juju4/ansible-viewfinderjs/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-viewfinderjs/actions?query=branch%3Adevel)

# viewfinderjs ansible role

Install Remote Browser Isolation ViewFinderJS
This is work in progress and not functional at this point

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
viewfinderjs_version: 111f6cb579e8d0cc4a7e39674eaca74f9460903c
```

## Continuous integration

This role has a GitHub action configuration along molecule.

```
$ pip install molecule docker
$ molecule test
$ MOLECULE_DISTRO=ubuntu:20.04 molecule test --destroy=never
```

## Troubleshooting & Known issues

* Warning! npm outdated and audit returns issues including command injection on May 2021.

* Warning! docker image is 2.41GB and latest 2.6 tags is 7 months old.

* `ChromeLauncher Waiting for browser.......................` in log
Likely systemd restrictions too strict. Ensure following options are not used:
InaccessiblePaths=/proc, RestrictNamespaces=~user mnt, SystemCallFilter

* `The setuid sandbox is not running as root. Common causes:`
result of systemd restrictions.

* For TLS support, certificates are needed in sslcert/{master,staging} directories.

* Only getting VF Logo, progress bar loading and ending, and nothing more.

## License

BSD 2-clause
