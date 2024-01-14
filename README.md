Install and configure Pi-hole
=========

The role installs and configures Pi-hole on a Raspberry Pi.

Role Variables
--------------

The ```pihole_ip_address``` variable should be set to the internal IP address of the server runnin Pi-Hole.

```pihole_admin_password``` should be set to the password for the Pi-Hole web interface.

```pihole_unbound_port``` can be set to the port Unbound is using.

The ```pihole_root_hints_url``` variable can be set to the URL of the root hints file.

Example Playbook
----------------

```yaml
    - hosts: servers
      vars:
        password: "password123"
      
      roles:
         - { role: pihole, pihole_admin_password: "{{ password }}" }
         - { role: pihole, pihole_admin_password: "{{ password }}",
             pihole_unbound_port: 5353, pihole_root_hints_url: https://www.internic.net/domain/named.root }
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
