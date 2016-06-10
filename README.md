# ansible-scripts
[ESIEE][Usine Logicielle] Scripts Ansible

Ce projet a pour but l'installation automatisée d'une usinge logicielle Java à l'aide des technologies Vagrant et Ansible. L'usine logicielle se composent de plusieurs outils d'aide au développement logiciel (compilation, dépendances, déploiement, etc), d'une infrastructure web (serveur Tomact, reverse proxy Apache) et d'une [application J2EE](https://github.com/harfangeek/api-tasks-java-ee).
Pour plus d'information voir la [documentation](https://github.com/harfangeek/ansible-scripts/blob/master/documentation.pdf).

- Installation de Vagrant + Ansible:
  - wget https://releases.hashicorp.com/vagrant/1.7.2/vagrant_1.7.2_x86_64.deb
  - dpkg -i vagrant_1.7.2_x86_64.deb
  - apt-get install ansible virtualbox virtualbox-dkms

- Lancer la VM:
  - git clone https://github.com/harfangeek/ansible-scripts.git
  - cd ansible-scripts
  - vagrant up : Télécharge et installe la VM, execute le playbook ansible lors de la première mise en route
  - Services accessibles depuis le host:
    - Jenkins : http://localhost:8080/jenkins
      - Build configuré: récupère l'application sur github, compile et déploie sur tomcat
    - Tomcat : http://localhost:8080/tomcat
    - Application : http://localhost:8080/tomcat/tasks-server

- Gestion de la VM:
  - vagrant provision : executer le script ansible une nouvelle fois
  - vagrant ssh : ouvre une session ssh sur la VM
  - vagrant halt : arrête la VM
  - vagrant reload : reboot la VM
  - virtualbox : Gérer la VM via Virtualbox (snapshot, etc).
  
- Commandes ansible:
  - ansible all -m ping : Teste si les hosts sont accessibles (hosts définit dans la configuration d'Ansible)
  - ansible all -i hosts --list-hosts : Liste les hosts définits dans le fichier "hosts" local
  - ansible all -i hosts -m ping : Test si les hosts définit dans le fichier "hosts" local sont accessibles
  - ansible-playbook install_all.yml -i hosts -k : Lance le playbook install_all.yml pour tous les hosts du fichier "hosts"
  

