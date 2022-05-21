## 使用 GitHub 仓库

```
~]# vim requirements.yml
---
roles:
  - src: https://github.com/dengyouf/Ansible-Galaxy-Motd.git
    scm: git
    version: main
```

```
~]# ansible-galaxy install -r requirements.yml
- extracting Ansible-Galaxy-Motd to /root/.ansible/roles/Ansible-Galaxy-Motd
- Ansible-Galaxy-Motd (main) was installed successfully
```

- ` ansible-playbook -i .ansible/roles/Ansible-Galaxy-Motd/tests/inventory  .ansible/roles/Ansible-Galaxy-Motd/tests/test.yml`

## 使用 Galaxy Server `https://galaxy.ansible.com/`

### 方式1

```
~]# ansible-galaxy install dengyouf.ansible_galaxy_motd
- downloading role 'ansible_galaxy_motd', owned by dengyouf
- downloading role from https://github.com/dengyouf/Ansible-Galaxy-Motd/archive/main.tar.gz
- extracting dengyouf.ansible_galaxy_motd to /root/.ansible/roles/dengyouf.ansible_galaxy_motd
- dengyouf.ansible_galaxy_motd (main) was installed successfully
```

```
~]# ansible-galaxy list
# /root/.ansible/roles
- ansible-galaxy-demo, main
- dengyouf.ansible_galaxy_motd, main
# /usr/share/ansible/roles
# /etc/ansible/roles
```

```
~]# ansible-playbook -i inventory  site_test.yml
```

```
 ~]# ansible-galaxy remove dengyouf.ansible_galaxy_motd
```

### 方式 2

```
~]# vim site_requirements.yml
---
roles:
  - src: dengyouf.ansible_galaxy_motd
    version: main
```

```
~]# ansible-galaxy install -r site_requirements.yml
- downloading role 'ansible_galaxy_motd', owned by dengyouf
- downloading role from https://github.com/dengyouf/Ansible-Galaxy-Motd/archive/main.tar.gz
- extracting dengyouf.ansible_galaxy_motd to /root/.ansible/roles/dengyouf.ansible_galaxy_motd
- dengyouf.ansible_galaxy_motd (main) was installed successfully
```
```
~]# ansible-playbook -i inventory  site_test.yml
```

```
 ~]# ansible-galaxy remove dengyouf.ansible_galaxy_motd
```
