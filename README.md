# [locale](#locale)

Configure locale on your system.

|Travis|GitHub|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![travis](https://travis-ci.com/robertdebock/ansible-role-locale.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-locale)|[![github](https://github.com/robertdebock/ansible-role-locale/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-locale/actions)|[![quality](https://img.shields.io/ansible/quality/35991)](https://galaxy.ansible.com/robertdebock/locale)|[![downloads](https://img.shields.io/ansible/role/d/35991)](https://galaxy.ansible.com/robertdebock/locale)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-locale.svg)](https://github.com/robertdebock/ansible-role-locale/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.locale
```

The machine may need to be prepared using `molecule/resources/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
    - role: robertdebock.bootstrap
```

For verification `molecule/resources/verify.yml` run after the role has been applied.
```yaml
---
- name: Verify
  hosts: all
  become: yes
  gather_facts: yes

  tasks:
    - name: check if connection still works
      ping:
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for locale

# Set one locale from the output of the shell command `locale -a`.
# A few common locales: en_US.UTF-8, nl_NL.utf8, C.utf8, POSIX

locale_lang: en_US.UTF-8
locale_language: "{{ locale_lang }}"
locale_lc_address: "{{ locale_lang }}"
locale_lc_all: "{{ locale_lang }}"
locale_lc_collate: "{{ locale_lang }}"
locale_lc_ctype: "{{ locale_lang }}"
locale_lc_identification: "{{ locale_lang }}"
locale_lc_measurement: "{{ locale_lang }}"
locale_lc_messages: "{{ locale_lang }}"
locale_lc_monetary: "{{ locale_lang }}"
locale_lc_name: "{{ locale_lang }}"
locale_lc_numeric: "{{ locale_lang }}"
locale_lc_paper: "{{ locale_lang }}"
locale_lc_response: "{{ locale_lang }}"
locale_lc_telephone: "{{ locale_lang }}"
locale_lc_time: "{{ locale_lang }}"
```

## [Requirements](#requirements)

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the current, previous and next release of Ansible.)

The following roles can be installed to ensure all requirements are met, using `ansible-galaxy install -r requirements.yml`:

```yaml
---
- robertdebock.bootstrap

```

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/locale.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|alpine|all|
|amazon|2018.03|
|el|7, 8|
|debian|buster, bullseye|
|fedora|31, 32|
|opensuse|all|
|ubuntu|focal, bionic, xenial|

The minimum version of Ansible required is 2.8 but tests have been done to:

- The previous version, on version lower.
- The current version.
- The development version.



## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-locale) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-locale/issues)

Testing is done using [Tox](https://tox.readthedocs.io/en/latest/) and [Molecule](https://github.com/ansible/molecule):

[Tox](https://tox.readthedocs.io/en/latest/) tests multiple ansible versions.
[Molecule](https://github.com/ansible/molecule) tests multiple distributions.

To test using the defaults (any installed ansible version, namespace: `robertdebock`, image: `fedora`, tag: `latest`):

```
molecule test

# Or select a specific image:
image=ubuntu molecule test
# Or select a specific image and a specific tag:
image="debian" tag="stable" tox
```

Or you can test multiple versions of Ansible, and select images:
Tox allows multiple versions of Ansible to be tested. To run the default (namespace: `robertdebock`, image: `fedora`, tag: `latest`) tests:

```
tox

# To run CentOS (namespace: `robertdebock`, tag: `latest`)
image="centos" tox
# Or customize more:
image="debian" tag="stable" tox
```

## [License](#license)

Apache-2.0


## [Author Information](#author-information)

[Robert de Bock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
