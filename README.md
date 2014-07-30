Stouts.users
============

[![Build Status](https://travis-ci.org/Stouts/Stouts.users.png)](https://travis-ci.org/Stouts/Stouts.users)

Ansible role which Manage users and groups

#### Variables
```yaml
users_enabled: yes              # The role is enabled

users_groups: []                # Create groups
                                # Simple syntax:
                                #   users_groups: [name1, name2]
                                # Complex syntax:
                                #   users_groups:
                                #     - name: name1
                                #       system: yes
                                #     - name: name2

users_users: []                 # Create users
                                # Simple syntax:
                                #   users_users: [name1, name2]
                                # Complex syntax:
                                #   users_users:
                                #     - name: name1
                                #       groups: admin,sudo
                                #       shell: /bin/zsh
                                #       ssh_keys:
                                #         - ssh-rsa KEY-WILL-BE-ADDED-TO-AUTHORIZED-KEYS

users_shell: /bin/bash          # Default user shell

users_remove_users: []          # List of user names which will be removed
users_remove_groups: []         # List of group names which will be removed
```

#### Usage

Add `Stouts.users` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.users

  vars:
    users_groups: [admin]
    users_users:
      - name: klen
        ssh_keys:
          - ssh-rsa KEY-HERE

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.users/issues)!

