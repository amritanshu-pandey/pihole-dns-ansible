Pihole Personal DNS
===================

Manage personal DNS entries using Pihole

Requirements
------------

- Pihole

Role Variables
--------------

- `pihole_dns_lan_list_file`: File where Pihole custom DNS entries should be managed [default - /etc/pihole/lan.list]
- `pihole_dns_dnsmasq_conf`: Pihole internal dnsmasq config file for managin personal DNS [default - /etc/dnsmasq.d/02-lan.conf]
- `pihole_dns_entries`: Custom DNS entries in the following format:
    ```yml
    pihole_dns_entries:
      - ip: 192.168.1.3
        fqdn: random.example.com
        host: random
    ```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
---
- hosts: pihole.example.com
  name: Update pihole DNS entries
  become: true
  connection: remote
  vars:
    pihole_dns_entries:
      - ip: 192.168.1.2
        fqdn: random.example.com
        host: random
      - ip: 192.168.1.3
        fqdn: anotherrandom.example.com
        host: anotherrandom
  roles:
    - pihole-personal-dns 
```

License
-------

BSD

Author Information
------------------

Name: Amritanshu Pandey <email@amritanshu.in>
