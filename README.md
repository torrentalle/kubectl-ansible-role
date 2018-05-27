kubectl-ansible-role
=========

This role installs [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) binary

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

 * **kubectl_release**: Define *kubectl* release to install. Default `latest`
 * **kubectl_install_path**: Where to install *kubectl* binary. Default `/usr/local/bin`

You can change the installation sources modifying following variables.

 * **kubectl_latest_info_url**: https://storage.googleapis.com/kubernetes-release/release/stable.txt
 * **kubectl_download_url**: "https://storage.googleapis.com/kubernetes-release/release/{{ kubectl_release }}/bin/{{ ansible_system | lower }}/amd64/kubectl"
 * **kubectl_sha1_url**: "{{ kubectl_download_url }}.sha1"


Usage
----------------

```
    - hosts: bastion
      roles:
         - { role: kubectl }
```

License
-------

BSD

Author
------------------
 * **[torrentalle](https://github.com/torrentalle)**
