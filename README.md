Stouts.resources
================

[![Build Status](https://travis-ci.org/Stouts/Stouts.resources.png)](https://travis-ci.org/Stouts/Stouts.resources)

Ansible role (copy files from your inventory directory to remote server)

The role copied all files from your inventory directory to server (by default
/etc/ansible/resources). By example if you would like copy your deploy keys,
configuration files you dont need write additional ansible tasks.

#### Variables
```yaml
resources_enabled: yes                        # Enable the role
resources_from: "{{inventory_dir}}/resources" # Local resources directory (files will be copied from)
resources_to: /etc/ansible                    # Remote resources directory (files will be copied to)
resources_clean: no                           # Delete remote resources directory
```

#### Usage

Add `Stouts.resources` to your roles. Create `<inventory_dir>\resources`
directory and place your files here.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.resources
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.resources/issues)!
