ansible-role-users [![Build Status](https://travis-ci.org/honeylogic-io/ansible-role-users.svg?branch=master)](https://travis-ci.org/honeylogic-io/ansible-role-users)
=========

An opinionated role on managing unix users.

Role Variables
--------------

```yml
user_shell: /bin/zsh
```

The default shell when not specified.

```
user_groups: [sudo, docker]
```

The default user groups when not specified.

```
user_passwordless_sudo: true
```

Passwordless sudo by default.

To override the defaults set the variable without the `user_` prefix for each
user. E.g

```yaml
- role: ansible-role-users
  vars:
    users:
      - name: dani
        ssh_public_key: XXXX
        groups: [developers]
        passwordless_sudo: false
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ansible-role-users
      vars:
        users:
          - name: dani
            ssh_public_key: XXXX
```

License
-------

MIT
