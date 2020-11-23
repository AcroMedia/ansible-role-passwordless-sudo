# ansible-role-passwordless-sudo

![.github/workflows/molecule.yml](https://github.com/AcroMedia/ansible-role-passwordless-sudo/workflows/.github/workflows/molecule.yml/badge.svg)

Configure the list of users and/or groups that can run sudo commands without a password.

## Warning

Some automation systems require passwordless sudo in order to function in certain scenarios. Letting any user operate sudo without a password strips an important layer of security from your system, and is not recommended for general use. Make sure you've compensated for the increased risk with additional layers of protection to your system, such as removing default users, blocking ssh access, disabling password logins, password-protecting private ssh keys, etc.

## Requirements

- OS: Debian or Red Hat
- Sudo installed

## Role Variables

#### `passwordless_sudo_users` (list)
- Defaults to empty `[]`.

#### `passwordless_sudo_groups` (list)
- Defaults to empty `[]`

## Dependencies

None.

## Example Playbook

```yaml
- hosts: servers
  gather_facts: true
  become: true
  vars:
    passwordless_sudo_users:
      - lskywalker
    passwordless_sudo_groups:
      - automators
  roles:
    - name: Configure passwordless sudoers
      role: acromedia.passwordless-sudo
```

## License

GPLv3

## Author Information

[Acro Media Inc](https://www.acromedia.com/)
