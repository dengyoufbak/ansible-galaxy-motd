- `vim requirements.yml`

```
---
roles:
  - src: https://github.com/dengyouf/Ansible-Galaxy-Motd.git
    scm: git
    version: main
```

- `ansible-galaxy install -r requirements.yml`

```
- extracting Ansible-Galaxy-Motd to /root/.ansible/roles/Ansible-Galaxy-Motd
- Ansible-Galaxy-Motd (main) was installed successfully
```

- ` ansible-playbook -i .ansible/roles/Ansible-Galaxy-Motd/tests/inventory  .ansible/roles/Ansible-Galaxy-Motd/tests/test.yml`
