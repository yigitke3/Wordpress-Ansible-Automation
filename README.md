# Wordpress-Ansible-Automation

A compilation of Ansible roles to install a WordPress Stack on **RHEL 9 / CentOS Stream 9** and **Ubuntu 24.04** systems.

## Features

- **Multi-OS Support:** Deploys WordPress + Apache + PHP + MariaDB on:
  - RHEL 9 / CentOS Stream 9
  - Ubuntu 24.04 LTS
- **Modern Ansible:** Refactored to use modern Ansible modules and syntax.
- **Secure Configuration:** Prompts for database passwords during execution to prevent hardcoding secrets.

## Prerequisites

- Ansible installed on the control node.
- Target servers with SSH access and sudo privileges.

## Usage

1.  **Configure Hosts:**
    The `hostsexample` file is configured for `localhost` by default. Update it with your target server IP addresses if deploying remotely.

    Default `hostsexample`:
    ```ini
    [wordpress]
    localhost ansible_connection=local ansible_python_interpreter=/usr/bin/python3
    ```
    *Note: The `ansible_python_interpreter` is set to `/usr/bin/python3` to ensure compatibility with system-level packages (like `python3-mysqldb` or `python3-PyMySQL`) which are required for database operations.*

2.  **Run the Playbook:**
    Run the playbook and follow the prompts to enter the MySQL root password and the WordPress database password.

    ```bash
    ansible-playbook -i hostsexample wordpressplaybook.yml
    ```

    You will be prompted:
    ```
    Enter MySQL Root Password:
    Enter WordPress Database Password:
    ```

    **Non-Interactive Mode (for automation/testing):**
    You can bypass the prompts by passing variables directly using `-e`:
    ```bash
    ansible-playbook -i hostsexample wordpressplaybook.yml \
      -e "mysql_root_password=your_secure_root_password" \
      -e "wordpress_dbpass=your_secure_db_password"
    ```

## Role Variables

Variables are defined in `roles/ansiblewordpress/vars/`.
- `main.yml`: Common variables (WordPress DB Name, User, etc). **Note:** Passwords are no longer defined here to prioritize secure prompts.
- `RedHat/main.yml`: RHEL/CentOS specific package names.
- `Debian/main.yml`: Debian/Ubuntu specific package names.

Happy blogging.
