# [Ansible role packer](#ansible-role-packer)

Packer for Linux

|GitHub|Issues|Pull Requests|Version|Downloads|
|------|------|-------------|-------|---------|
|[![github](https://github.com/buluma/ansible-role-packer/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-packer/actions/workflows/molecule.yml)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-packer.svg)](https://github.com/buluma/ansible-role-packer/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-packer.svg)](https://github.com/buluma/ansible-role-packer/pulls/)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-packer.svg)](https://github.com/buluma/ansible-role-packer/releases/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/packer)](https://galaxy.ansible.com/ui/standalone/roles/buluma/packer/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-packer/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  become: true
  hosts: all
  pre_tasks:
    - name: Update apt cache.
      ansible.builtin.apt:
        update_cache: "true"
        cache_valid_time: "600"
      when: ansible_os_family == 'Debian'
  roles:
    - role: buluma.packer
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-packer/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  become: true
  gather_facts: false
  hosts: all
  roles:
    - role: buluma.bootstrap
    - role: buluma.ca_certificates
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-packer/blob/master/defaults/main.yml):

```yaml
---
packer_arch: amd64
packer_bin_path: /usr/local/bin
packer_version: "1.0.0"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-packer/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub |
|-------------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Build Status GitHub](https://github.com/buluma/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-packer/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-packer/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-packer/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

