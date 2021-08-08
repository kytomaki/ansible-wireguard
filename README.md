![Ansible lint](https://github.com/kytomaki/ansible-wireguard/actions/workflows/ansible-lint.yml/badge.svg)

Wireguard
=========

Create a mesh network for group of hosts.

Requirements
------------

Currenty works on debian buster.

Role Variables
--------------

Each of the host should be in group `wireguard` andhave `wireguard_ip` in their `hostvars`

```
[wireguard]
alpha wireguard_ip=10.0.10.1
beta wireguard_ip=10.0.10.2
ceylon wireguard_ip=10.0.10.3
```

* `wireguard_preshared_key`: preshared key for extra security (optional)
* `extra_peers`: a list of extra peers (optional)

For example:

```yaml
---
extra_peers:
 - public_key: public_key_of_the_extra_peer_goes_here # mandatory
   allowed_ips: 10.0.0.1/32                           # mandatory
   pre_shared_key: pre_shared_key_of_peer_goes_here   # optional
```

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

Samppa Kytömäki <kytomaki@iki.fi>
