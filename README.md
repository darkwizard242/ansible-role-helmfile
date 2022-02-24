[![build-test](https://github.com/darkwizard242/ansible-role-helmfile/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-helmfile/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-helmfile/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-helmfile/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/47488?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/47488?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/47488?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-helmfile&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-helmfile) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-helmfile?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-helmfile?color=orange&style=flat-square)

# Ansible Role: helmfile

Role to install (_by default_) [helmfile](https://github.com/roboll/helmfile) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
helmfile_app: helmfile
helmfile_version: 0.143.0
helmfile_os: linux
helmfile_arch: amd64
helmfile_dl_url: https://github.com/roboll/{{ helmfile_app }}/releases/download/v{{ helmfile_version }}/{{ helmfile_app }}_{{ helmfile_os }}_{{ helmfile_arch }}
helmfile_bin_path: /usr/local/bin
helmfile_file_owner: root
helmfile_file_group: root
helmfile_file_mode: '0755'
```

### Variables table:

Variable            | Description
------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------
helmfile_app        | Defines the app to install i.e. **helmfile**
helmfile_version    | Defined to dynamically fetch the desired version to install. Defaults to: **6.5.0**
helmfile_os         | Defines os type. Used for obtaining the correct type of binaries based on OS type. Defaults to: **linux**
helmfile_arch       | Defines os architecture. Used to set the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
helmfile_dl_url     | Defines URL to download the helmfile binary from.
helmfile_bin_path   | Defined to dynamically set the appropriate path to store helmfile binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
helmfile_file_owner | Owner for the binary file of helmfile.
helmfile_file_group | Group for the binary file of helmfile.
helmfile_file_mode  | Mode for the binary file of helmfile.

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
    helmfile_version: 0.142.0
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
