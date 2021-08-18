# TP : installer un cluster simple Elasticsearch et Kibana avec Ansible

Pour utiliser ce dépôt :

- installer ansible, vagrant et virtualbox.
- creer les VMs: `vagrant up`
- lancer le playbook pour tester les VM avec Ansible: `vagrant provision`
- installer elastic: `ansible-playbook setup_elastic.yml`
- installer elastic: `ansible-playbook setup_kibana.yml`
