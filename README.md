# ansible-scripts
[ESIEE][Usine Logicielle] Scripts Ansible

- Installation de Vagrant + Ansible:
  - wget https://releases.hashicorp.com/vagrant/1.7.2/vagrant_1.7.2_x86_64.deb
  - dpkg -i vagrant_1.7.2_x86_64.deb
  - apt-get install ansible virtualbox virtualbox-dkms

- Lancer la VM:
  - git clone https://github.com/harfangeek/ansible-scripts.git
  - vagrant up : Télécharge et installe la VM, execute le playbook ansible lors de la première mise en route
  - vagrant provision : executer le scritp ansible une nouvelle fois
  - vagrant ssh : ouvre une session ssh sur la VM
  - vagrant halt : arrête la VM
  - vagrant reload : reboot la VM
  - virtualbox : Gérer la VM via Virtualbox (snapshot, etc).
  
- Commandes ansible:
  - ansible all -m ping : Teste si les hosts sont accessibles (hosts définit dans la configuration d'Ansible)
  - ansible all -i hosts --list-hosts : Liste les hosts définits dans le fichier "hosts" local
  - ansible all -i hosts -m ping : Test si les hosts définit dans le fichier "hosts" local sont accessibles
  - ansible-playbook install_all.yml -i hosts -k : Lance le playbook install_all.yml pour tous les hosts du fichier "hosts"
  

