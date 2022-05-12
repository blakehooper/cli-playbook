# cli-playbook
Playbook for configuring cli

## Instructions

Checkout 3rd party dependencies

```zsh
mkdir roles && cd roles
git clone https://github.com/gantsign/ansible-role-oh-my-zsh.git
```

Note: git ignoring any file named *inventory.yaml in this directory
Create inventory like:

#### **`inventory.yaml`**
```yaml
---
shell_users:
  hosts:
    vm:
      ansible_host: 192.168.122.72
      ansible_user: blake
      other_users:
        - subaccount
```

And run playbook:

```zsh
ansible-playbook -i ./inventory.yaml --ask-become-pass ./setup_shell.yaml
```

