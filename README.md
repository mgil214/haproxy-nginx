# haproxy-nginx
Creating HAproxy loadbalancing to two Nginx servers.

Describtion. 

This set of Ansible playbooks and roles execute installation and configuration of simple "proof-of-concept" type of the Web service. There is one load balancer based on HAproxy and two Nginx web servers behind it.

Prerequisites.

1. Three servers with CentOS 6.x installed.
According to the Test describtion there are three CentOS 6 hosts. So all playbooks, tasks and settings are set to work exactly with this type of OS. I can add OS recognition function in Ansible but since it is not required I left it as is to save Time and avoid extra lines of code.

2. According to the task there are following host names and IPv4 addresses set:
Test1 - 192.168.30.1
Test2 - 192.168.30.2
Test3 - 192.168.30.3
Because of that I made an inventory "hosts" file with hardcoded IP addresses for the sake of time saving.

3. Hosts mentioned above have necessary public ssh keys added to the directory "~/.ssh/authorized_keys" of the user under which ssh connection is meant to be in order to Ansible playbooks work.

4. There are necessary packages like ansible and python installed on the system from which playbooks are going to be executed.


Execution.

The execution of the playbook is quite straitforward.

ansible-playbook deploy.yml -i hosts -u <USERNAME>

It is also possible to to copy the "hosts" file to /etc/ansible/ directory. After that it is possibly just run
"ansible-playbook deploy.yml" command with the username provided if needed.
If the username is equal to th remote user then it is not necessary.

It is also possible to run one of playbooks for either haproxy settings or nginx settings only. Filenames are:
haproxy.yml
nginx.yml


As far as I tested everything should work just fine.
Enjoy :-)
