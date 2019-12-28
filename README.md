# Pixelflut

Small Ansible role to configure a Pixelflut ([the pixelpwnr server implementation](https://github.com/timvisee/pixelpwnr-server))server on a Debian 10 based system.

## Requirements

This assumes a server with a Debian 10 net install image and the possibility for the user to log in with permissions for sudo.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

## Example Playbook

This is an example of how to use the role:
```
    - hosts: server
      roles:
         - { role: pixelflut }
```

License
-------

MIT
