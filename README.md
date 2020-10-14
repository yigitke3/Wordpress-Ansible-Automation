# Wordpress-Ansible-Automation
A simple compilation of Ansible roles to install WordPress Stack on CentOs 7

WordPress+Apache+PHP+MariaDB Deployment with required dependencies on CentOs7

Playbooks deploy a simple all-in-one WordPress configuration ready to be configured after the installation.

Update the hosts file under /etc/ansible directory to include the names or URL's of the servers you want to deploy. There is one example hosts file in the repository.

Upload your private ssh key under this path: /home/opc/.ssh/"your_key"

Then run the playbook with the below command:

ansible-playbook wordpressplaybook.yml

Happy blogging.
