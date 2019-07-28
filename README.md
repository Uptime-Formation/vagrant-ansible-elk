# TP : installer un cluster simple Elasticsearch et Kibana avec Ansible

Correction dans la branche: `correction_elastic_install_vagrant`

pour utiliser ce dépôt sur la branche correction:
- installer ansible, vagrant et virtualbox.
- creer les VMs: `vagrant up`
- lancer le playbook pour tester les VM avec Ansible: `vagrant provision` 
- installer elastic: `ansible-playbook setup_elastic.yml`
- installer elastic: `ansible-playbook setup_kibana.yml`