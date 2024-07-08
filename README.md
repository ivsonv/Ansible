# Ansible
A powerful tool for `applying configurations`, which can be used in `conjunction` with `terraform`.<br>
`Ansible` provides open-source automation that reduces complexity and runs everywhere.<br>
Using Ansible lets you automate virtually any task

* Eliminate repetition and simplify workflows
* Manage and maintain system configuration
* Continuously deploy complex software
* Perform zero-downtime rolling updates

* [Docs Ansible](https://docs.ansible.com/ansible/10/getting_started/index.html)

### Start Local

* inventory -> hosts -> `localhost ansible_connection=local`
![Captura de Tela 2024-07-03 às 20 35 58](https://github.com/ivsonv/Ansible/assets/63156114/7d5a7c61-6853-47af-9d51-fc2975904b03)

### Exec commands
* When starting the nodes, you must enable ssh on the node
```sh
service ssh start
```

* Install package `git` in nodes
```sh
ansible -i hosts all -m apt -a "update_cache=yes name=git state=present"
```

* Remove package `git` in nodes
```sh
ansible -i hosts all -m apt -a "update_cache=yes name=git state=absent"
```

* checkout in repository
```sh
ansible -i hosts all -m git -a "repo=https://github.com/ivsonv/provision-terraform-iac dest=/root/terraform-repo"
```

* full informations the node
```sh
ansible -i hosts node_ansible -m setup
```