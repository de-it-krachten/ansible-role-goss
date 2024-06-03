[![CI](https://github.com/de-it-krachten/ansible-role-goss/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-goss/actions?query=workflow%3ACI)


# ansible-role-goss

Installs goss, quick and Easy server testing/validation<br>
https://goss.rocks<br>
https://github.com/goss-org/goss<br>



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 39
- Fedora 40

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Github CLI - API
goss_api: https://api.github.com/repos/goss-org/goss

# Github CLI - repo
goss_repo: https://github.com/goss-org/goss

# Lookup table for architecture
goss:
  architecture:
    x86_64: amd64
    i386: 386
    aarch64: arm64
  system:
    Linux: linux
    Darwin: darwin

# Version of the CLI to install
goss_version: latest

# Binary file to download
goss_file: "goss-{{ goss_system }}-{{ goss_architecture }}"

# Location/ownership/permissions of the binary
goss_path: /usr/local/bin/goss
goss_owner: root
goss_group: root
goss_mode: '0755'
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'goss'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'goss'
      ansible.builtin.include_role:
        name: goss
</pre></code>
