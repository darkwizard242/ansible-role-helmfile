[![build-test](https://github.com/darkwizard242/ansible-role-helmfile/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-helmfile/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-helmfile/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-helmfile/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/d/darkwizard242/helmfile) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-helmfile?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-helmfile?color=orange&style=flat-square)

# Ansible Role: helmfile

Role to install (_by default_) [helmfile](https://github.com/helmfile/helmfile) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
helmfile_app: helmfile
helmfile_version: 0.169.1
helmfile_os: "{{ ansible_system | lower }}"
helmfile_architecture_map:
  amd64: amd64
  arm: arm64
  x86_64: amd64
  armv6l: armv6
  armv7l: armv7
  aarch64: arm64
  32-bit: "386"
  64-bit: amd64
helmfile_dl_url: https://github.com/helmfile/{{ helmfile_app }}/releases/download/v{{ helmfile_version }}/{{ helmfile_app }}_{{ helmfile_version }}_{{ helmfile_os }}_{{ helmfile_architecture_map[ansible_architecture] }}.tar.gz
helmfile_bin_path: /usr/local/bin
helmfile_file_owner: root
helmfile_file_group: root
helmfile_file_mode: '0755'
```

### Variables table:

Variable                  | Description
------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------
helmfile_app              | Defines the app to install i.e. **helmfile**
helmfile_version          | Defined to dynamically fetch the desired version to install. Defaults to: **0.169.1**
helmfile_os               | Defines os type. Used for obtaining the correct type of binaries based on OS type.
helmfile_architecture_map | Defines os architecture. Used to set the correct type of binaries based on OS System Architecture.
helmfile_dl_url           | Defines URL to download the helmfile binary from.
helmfile_bin_path         | Defined to dynamically set the appropriate path to store helmfile binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
helmfile_file_owner       | Owner for the binary file of helmfile.
helmfile_file_group       | Group for the binary file of helmfile.
helmfile_file_mode        | Mode for the binary file of helmfile.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **helmfile**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helmfile
```

For customizing behavior of role (i.e. specifying the desired **helmfile** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helmfile
  vars:
    helmfile_version: 0.163.0
```

For customizing behavior of role (i.e. placing binary of **helmfile** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.helmfile
  vars:
    helmfile_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-helmfile/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
