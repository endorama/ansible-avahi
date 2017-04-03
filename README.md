Ansible role: avahi
=========

Install and configure avahi-daemon.

Requirements
------------

Ansible `hash_behaviour` should be set to `merge`.

Role Variables
--------------


- `avahi__hostname`: (string)  
  avahi hostname  
  default: $ansible_nodename
- `avahi__domain`: (string)  
  avahi domain  
  default: local
- `avahi__useipv4`: (string)
  if avahi should bind to ipv4 address should be 'yes' of 'no' as **string**  
  default: 'yes'
- `avahi__useipv6`: (string)  
  if avahi should bind to ipv4 address should be 'yes' of 'no' as **string**  
  default: 'no'

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  become: yes
  vars:
    hostname: login # hostname will be used by avahi role as $ansible_nodename
    avahi__domain: example.local # subdomain too! Yay!

  pre_tasks:
    - name: set hostname
      hostname: name={{hostname}}
  
  roles:
    - avahi
```

License
-------

MIT

Author Information
------------------

Edoardo Tenani - [http://about.me/edoardo.tenani](http://about.me/edoardo.tenani)
