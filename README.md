# Ansible-Porject

Mastodon Ansible Playbook
This Ansible playbook automates the installation and configuration of Mastodon on a server. It can be used to set up a new instance or upgrade an existing one.

Prerequisites
Before running the playbook, you need:

A control node with Ansible installed.
At least one target node running a Debian-based Linux distribution (e.g. Debian, Ubuntu).
Installing Ansible
If Ansible is not already installed on the control node, you can install it with the following command:

--- 

sudo apt-get update && sudo apt-get install ansible

---

Configuration
To use this playbook, you need to update the following variables in vars/mastodon.yml:

mastodon_version: The version of Mastodon to install.
You can also update the following variables in vars/postgresql.yml and vars/mastodon.yml to customize the installation:

postgresql_db_name: The name of the PostgreSQL database to create.
postgresql_db_user: The username for the PostgreSQL database user.
postgresql_db_password: The password for the PostgreSQL database user.
mastodon_domain: The domain name for your Mastodon instance.
mastodon_email: The email address for the Mastodon administrator.
mastodon_smtp_server: The hostname of the SMTP server to use for sending emails.
mastodon_smtp_username: The username to authenticate with the SMTP server.
mastodon_smtp_password: The password to authenticate with the SMTP server.
mastodon_smtp_from_address: The email address to use as the "From" address for outgoing emails.
Running the playbook
To run the playbook, execute the following command on the control node:

---

ansible-playbook -i hosts.ini mastodon.yml

--- 
This will run the playbook and configure the target node(s) with Mastodon.

Notes
This playbook assumes that you have already set up DNS records for your Mastodon instance and pointed them to the IP address of the target node(s).
This playbook assumes that you have already generated SSL certificates for your Mastodon instance and placed them in the files directory (named ssl.crt and ssl.key, respectively). If you don't have SSL certificates, you can generate them using a tool like Let's Encrypt.