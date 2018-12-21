# cluster-rabbitmq

This repository has a dockerfile to create the rabbitmq-server image with docker build or you can opt to use ansible-playbooks. There is a playbook for each instance, to connect correctly you will need to set up the path to the ssh key and also the public IPs.

If you want to change the name of the nodes or hostnames or the name of the images tags etc, all of those variables are inside vars.yml.

if you don't opt to use ansible-playbooks, you will need to connect manually to each instance and install docker-ce inside, also you will need to build the image manually and then run the container.

The command to run the container is inside the file called temp, you can copy paste in the command line to make it easier. But it's recommended to just use the playbooks.

To run the playbooks you need to use:
    ansible-playbook -i hosts <node_#>.yml

The playbook node1.yml, is for the "master" node, it doesn't add the other nodes' hosts so beware of that.

They are all inside the folder Manual playbooks.

There is a more elegant way, we can use ansible-galaxy to create roles. with them we will only need to run the ansible-playbook command once.

To run it we need to use:
    
    ansible-playbook -i hosts main.yml
