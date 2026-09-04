Base
====
Baseline host preparation: apt package updates, automatic security updates via unattended-upgrades, and SSH hardening (disables root login and password authentication).

Requirements
------------
None beyond ansible-core. Uses only `ansible.builtin` modules. The `validate` step on the SSH hardening task requires `sshd` to be present on the target (present by default on Debian).

Role Variables
--------------
Defined in `defaults/main.yml`:

- `base_apt_upgrade_type` (default: `safe`) — apt upgrade mode; `safe` upgrades without removing packages.
- `base_apt_cache_valid_time` (default: `3600`) — seconds apt cache is considered fresh before re-syncing.
- `base_unattended_upgrades_reboot` (default: `"true"`) — whether unattended-upgrades may reboot the host.
- `base_unattended_upgrades_reboot_with_users` (default: `"true"`) — allow auto-reboot even with users logged in.
- `base_unattended_upgrades_reboot_time` (default: `"04:00"`) — scheduled time for automatic reboots.
- `base_ssh_permit_root_login` (default: `"no"`) — value written to `PermitRootLogin`.
- `base_ssh_password_authentication` (default: `"no"`) — value written to `PasswordAuthentication`.

Dependencies
------------
None.

Example Playbook
----------------
    - hosts: servers
      roles:
         - base

License
-------
MIT-0

Author Information
------------------
Internal role — no external contact information.
