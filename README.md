# ansible-roles
Ansible roles. Intended for use as a sub-module.



### Github Authentication

```
> ~/.ssh/config
Host github
    HostName github.com
    User git
    IdentityFile ~/.ssh/github
    IdentitiesOnly yes
```
Move github key to `~/.ssh/github`

Set permissions: `chmod 600 ~/.ssh/github`

Add this repo to existing playbook, as a submodule:
```
cd ansible-playbooks
git submodule add github:aaron-imbrock/ansible-roles.git roles
git commit -m "Add roles as submodule"
git push
```
