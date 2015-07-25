antigen_zsh
===========

This role installs zsh and the Antigen framework.

Role Variables
--------------

```yaml
antigen_path: /usr/local/antigen  # where to install antigen
use_oh_my_zsh: true               # use oh-my-zsh
zsh_aliases: []                   # aliases to set
zsh_env_vars: []                  # environment variables to set
zsh_plugins: []                   # plugins to install
zsh_themes: []                    # themes to install
zsh_users: []                     # users to assign zsh as their default shell
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - antigen_zsh
  vars:
    antigen_path: "{{ ansible_env.HOME }}/.antigen"
    use_oh_my_zsh: true
    zsh_aliases:
      - { name: "ls", value: "ls -G", user: "all" }
      - { name: "nethack", value: "telnet nethack.alt.org", user: "barley" }
    zsh_env_vars:
      - { name: "PATH", value: "$PATH:/usr/bin:/bin:/usr/sbin:/usr/local/bin", user: "all" }
      - { name: "AWS_S3_BUCKET", value: "bazmut", user: "barley" }
    zsh_plugins:
      - { name: "git", user: "all" }
      - { name: "zsh-users/zsh-syntax-highlighting", user: "foozer" }
    zsh_themes:
      - { name: "gozilla", user: "foozer" }
      - { name: "arrow", user: "barley" }
    zsh_users:
      - foozer
      - barley
```

License
-------

Licensed under the MIT License. See the LICENSE file for details.

Author Information
------------------

- http://conpat.io
- andres@conpat.io
