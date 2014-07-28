Stouts.resources
================

[![Build Status](https://travis-ci.org/Stouts/Stouts.resources.png)](https://travis-ci.org/Stouts/Stouts.resources)

Ansible role (copy files from your inventory directory to remote server)

The role copied all files from your inventory directory to server (by default
/etc/ansible/resources). By example if you would like copy your deploy keys,
configuration files you dont need write additional ansible tasks.  Than you
could use them (make links to them, or copy remotelly)

See also: [Stouts.source](https://github.com/Stouts/Stouts.source)

#### Variables
```yaml
resources_enabled: yes                        # Enable the role
resources_from: "{{inventory_dir}}/resources" # Local resources directory (files will be copied from)
resources_to: /etc/ansible                    # Remote resources directory (files will be copied to)
resources_clean: no                           # Delete remote resources directory
```

#### Usage

Add `Stouts.resources` to your roles. Create `<inventory_dir>\resources`
directory and place your files here (`inventory_dir` is a directory where your
inventory file are placed). All files and directories from the directory will
be recursively copied to remote machine (by default to remote directory
`/etc/ansible`).

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
