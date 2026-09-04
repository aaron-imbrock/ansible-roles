Fail2ban
========
Installs and configures fail2ban with an SSH jail to block brute-force login attempts.

Requirements
------------
None beyond ansible-core. Uses only `ansible.builtin` modules.

Role Variables
--------------
Defined in `defaults/main.yml`:

- `fail2ban_ssh_maxretry` (default: `5`) — failed attempts before a ban.
- `fail2ban_ssh_bantime` (default: `1h`) — ban duration.
- `fail2ban_apt_cache_valid_time` (default: `3600`) — seconds apt cache is considered fresh before re-syncing. Kept independent from the `base` role's equivalent variable so this role has no cross-role dependency and can be applied standalone.

Dependencies
------------
None.

Example Playbook
----------------
    - hosts: servers
      roles:
         - fail2ban

License
-------
MIT-0

Author Information
------------------
Internal role — no external contact information.
