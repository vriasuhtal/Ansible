# Ansible
ansible directory

etc/ansible/hosts defould directory in Ansible master 

In Ansible three main type to excute the code as below
1) AD-hoc :- in adhoc we run one time command, this command are simple linux command
   there is no idempltancy
   eg:- ansible demo -a "ls" {demo is the group }
3) Module :- ansible ship with a no of module called module library
   Module can do single work
   idempotency we can run through command setup
   ansible demo -m setup yum -a "pkg=htppd state=present "
   
   eg"- if want to install the httpd then we can directly run using module
   ansible demo -b -m yum -a "pkg=htppd state=present " (if there is -m it shows its module)
5) playbook:-
   in playbook there is no of module and before install anything it will check the package is allredy there or not
   eg if we have task to
   install httpd, start the https server then we used ansbible palybook 



Ansible Role:-
it organise the ansible playbook 

sudo apt get install tree   #installation of tree structure of ansible role
sudo ansible-galaxy init web --offline         #rolename --web

---
#task file for web

- include: install.yml
- include: configure.yml
- include: service.yml

- sudo ansible-playbook site.yml --syntax-check to run site.yml
