when we create ansible playbook starts with -
mainly follows indentation 
list of tasks follows with -

- name: ping playbook
  hosts:
  tasks: 
  - name: ping the server
    ansible.builtin.ping:

what is ansible inventory?

Inventory is nothing but list of hosts and ansible server can connect with those hosts or nodes

