kubectl-ansible-role
=========
[![Build Status](https://travis-ci.org/torrentalle/kubectl-ansible-role.svg?branch=master)](https://travis-ci.org/torrentalle/kubectl-ansible-role)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-torrentalle.kubectl-blue.svg)](https://galaxy.ansible.com/torrentalle/kubectl-ansible-role)

This role installs [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) binary in all UNIX systems

Requirements
--------------
Ansible 2.2 or higher


Installation
--------------

Create or add to your roles dependency file (e.g requirements.yml):

```yml
- src: torrentalle.kubectl
```

Install the role with ansible-galaxy command:

```sh
ansible-galaxy install -p roles -r requirements.yml -f
```

Role Variables
--------------
Available variables are listed below, along with default values (see `defaults/main.yml`):

```yml
kubectl_release: 'latest'
kubectl_install_path: /usr/local/bin
```

You can change the installation sources modifying following variables (see `vars/main.yml`):

```yml
kubectl_latest_info_url: https://storage.googleapis.com/kubernetes-release/release/stable.txt
kubectl_download_url: "https://storage.googleapis.com/kubernetes-release/release/{{ kubectl_release }}/bin/{{ ansible_system | lower }}/amd64/kubectl"
kubectl_sha1_url: "{{ kubectl_download_url }}.sha1"
```

Usage
----------------

```yml
    - hosts: bastion
      roles:
         - { role: kubectl }
```

Testing
------------------

![Ansible](https://img.shields.io/badge/ansible-2.2-green.svg) ![Ansible](https://img.shields.io/badge/ansible-2.3-green.svg) ![Ansible](https://img.shields.io/badge/ansible-2.4-green.svg) ![Ansible](https://img.shields.io/badge/ansible-2.4-green.svg) ![Ansible](https://img.shields.io/badge/ansible-2.5-green.svg) ![Ansible](https://img.shields.io/badge/ansible-2.6.0a1-green.svg)

[Tox](https://tox.readthedocs.io), [Docker](https://www.docker.com/), [Molecule](https://molecule.readthedocs.io) and [Goss](https://goss.rocks) are used tot test this role.
You must install docker and tox before launch tests

```bash
sudo apt install docker-ce
sudo pip install tox
```

Run tests launching `tox` command

```bash
tox
```

License
-------

BSD

Author
------------------
 * **[torrentalle](https://github.com/torrentalle)**
