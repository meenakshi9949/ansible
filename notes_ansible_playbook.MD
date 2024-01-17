- we have to install ansible software in server that is called as ansible server
- ansible uses push based mechanism
- push based mechanism means when there is any change in server configuration it will push it to nodes
- no need to install agent software in nodes
- ansible server can connect to nodes through ssh
- we can create ansible playbooks by using yaml scripting (yet another markup language)
- when we create ansible playbook starts with (-)
- mainly follows indentation 
- list of tasks follows with (-)

- name: ping playbook
  hosts:
  tasks: 
  - name: ping the server
    ansible.builtin.ping:

what is ansible inventory?

Inventory is nothing but list of hosts and ansible server can connect with those hosts or nodes
192.187.56.9
192.187.56.9

[web] 
192.187.56.4
192.187.56.15

[catalogue]
192.187.56.10
192.187.56.23

[cart]
192.187.56.27
192.187.56.54

[roboshop:children]
web
catalogue
cart
command to execute inventory = ansible -i inventory web -list-hosts
command for all hosts in inventory file = ansible -i inventory all -list-hosts
ansible command for target hosts with playbook:
- have to mention host public ip address in palybooks hosts 
command: ansible-playbook -i inventory -e ansible_user=centos -e ansible_password=DevOps321 01-playbook.yaml