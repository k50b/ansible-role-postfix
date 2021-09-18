Ansible role: Postfix
=====================

A customized and self contained Postfix installation.

Sets up:
- Working Postfix configuration.
- A user for handling virtual mailboxes.
- Directory for virtual mailboxes.
- opendkim
  - Generates DKIM keys.
- Optionally configures relay hosts if we want to use it for select domains.

Requirements
------------

- A valid DNS configuration.
- A valid SSL cerficiate. By default uses "snake-oil" default self-signed cert. A default variable is provided to set path for cert and private key.
- `/etc/postfix/virtual` and `/etc/postfix/vmailbox` files need to be edited manually.
- Relay host needs to be set-up correctly if we want to use it.

Role Variables
--------------

```
postfix_myhostname: mail.example.com

postfix_virtual_domains:
  - example.com

postfix_cert_path: /etc/ssl/certs/ssl-cert-snakeoil.pem

postfix_privkey_path: /etc/ssl/private/ssl-cert-snakeoil.key

postfix_opendkim_genkey_selector: default

postfix_vmail_root_dir: /home/vmail

postfix_relay_maps: [] # {domain, mx, login, password}
```

Example Playbook
----------------

TODO

License
-------

MIT