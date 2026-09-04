Docker
======
Installs Docker Engine and the Compose plugin from Docker's official apt repository.

Requirements
------------
- Debian-based target host (uses the `apt` package manager and Docker's Debian apt repo).
- ansible-core >= 2.15, for the `ansible.builtin.deb822_repository` module used to register the repo and its signing key.

Role Variables
--------------
Defined in `defaults/main.yml`:

- `docker_packages` (default: `[docker-ce, docker-ce-cli, containerd.io, docker-compose-plugin]`) — packages installed.
- `docker_apt_repo_uri` (default: `https://download.docker.com/linux/debian`) — Docker's official apt repo base URL.
- `docker_apt_gpg_key_url` (default: `https://download.docker.com/linux/debian/gpg`) — signing key used to verify the repo.
- `docker_add_user_to_group` (default: `true`) — whether to add a user to the `docker` group for passwordless Docker commands.
- `docker_group_user` (default: `debian`) — the user added to the `docker` group when the above is enabled.

Dependencies
------------
None.

Example Playbook
----------------
    - hosts: servers
      roles:
         - docker

License
-------
MIT-0

Author Information
------------------
Internal role — no external contact information.
