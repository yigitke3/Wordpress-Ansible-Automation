# Wordpress-Ansible-Automation

A compilation of Ansible roles to install a WordPress Stack on **RHEL 9 / CentOS Stream 9** and **Ubuntu 24.04** systems.

## Features

- **Multi-OS Support:** Deploys WordPress + Apache + PHP + MariaDB on:
  - RHEL 9 / CentOS Stream 9
  - Ubuntu 24.04 LTS
- **Modern Ansible:** Refactored to use modern Ansible modules and syntax.

## Prerequisites

- Ansible installed on the control node.
- Target servers with SSH access and sudo privileges.

## Usage

1.  **Configure Hosts:**
    The `hostsexample` file is configured for `localhost` by default. Update it with your target server IP addresses if deploying remotely.

    Default `hostsexample`:
    ```ini
    [wordpress]
    localhost ansible_connection=local
    ```

2.  **Set Environment Variables:**
    For security, database passwords should be set via environment variables before running the playbook.

    ```bash
    export MYSQL_ROOT_PASSWORD="your_secure_root_password"
    export WORDPRESS_DB_PASSWORD="your_secure_db_password"
    ```

3.  **Run the Playbook:**
    ```bash
    ansible-playbook -i hostsexample wordpressplaybook.yml
    ```

## Role Variables

Variables are defined in `roles/ansiblewordpress/vars/`.
- `main.yml`: Common variables (Database passwords, WordPress config).
- `RedHat/main.yml`: RHEL/CentOS specific package names.
- `Debian/main.yml`: Debian/Ubuntu specific package names.

Happy blogging.
