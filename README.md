Wordpress Ansible automation on Ubuntu/CentOS

A compilation of Ansible roles to install a WordPress Stack on RHEL 9 / CentOS Stream 9 and Ubuntu 24.04 systems.

Features

Multi-OS Support: Deploys WordPress + Apache + PHP + MariaDB on:
RHEL 9 / CentOS Stream 9
Ubuntu 24.04 LTS
Refactored to use modern Ansible modules and syntax.

Prerequisites

Ansible installed on the control node.
Target servers with SSH access and sudo privileges.
Usage

Configure Hosts:
Update the hosts file (or /etc/ansible/hosts) with the IP addresses of your target servers. See hostsexample for reference.

SSH Key Setup:
Ensure your SSH key is deployed to the target servers.

Run the Playbook:

ansible-playbook -i <your_inventory_file> wordpressplaybook.yml
Role Variables

Variables are defined in roles/ansiblewordpress/vars/.

main.yml: Common variables (Database passwords, WordPress config).
RedHat/main.yml: RHEL/CentOS specific package names.
Debian/main.yml: Debian/Ubuntu specific package names.
Happy blogging.

Full Changelog: https://github.com/yigitke3/Wordpress-Ansible-Automation/commits/NewRelease
