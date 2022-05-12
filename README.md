# cli-playbook
Playbook for configuring cli

## Instructions

Checkout 3rd party dependencies

```zsh
mkdir roles && cd roles
git clone https://github.com/gantsign/ansible-role-oh-my-zsh.git
```

Create inventory like:

#### **`inventory.yaml`**
```yaml
---
shell_users:
  hosts:
    vm:
      ansible_host: 192.168.122.72
      ansible_user: blake
      tmux_autoconnect: true
      other_users:
        - subaccount
    localhost:
      ansible_host: localhost
      ansible_user: blake
      tmux_autoconnect: false
      ansible_connection: local      
```

Notes:

- git ignoring any file named *inventory.yaml in this directory
- tmux_autoconnect is weather to auto connect to an existing tmux session. true for remote servers, false for local.

And run playbook:

```zsh
ansible-playbook -i ./inventory.yaml --ask-become-pass ./setup_shell.yaml
```

