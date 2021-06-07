# Documentation

## About the project

Ulrich the Kubernetes builder is lightweight and simple Ansible playbooks for build an Kubernetes infrastructure. 

## Ansible architecture

```
group_vars/group1.yml -> here we assign variables to particular groups

host_vars/all.yml -> here we assign variables to particular systems

inventory/inventory_production -> inventory file for production servers

	/inventory_staging -> inventory file for staging environment

roles/prerequisite/ -> this herarchy represents a "role"

		  /defaults/main.yml -> default lower priority variables for this role

		  /files/foo.txt -> files for use with the copy resource

		  /handlers/main.yml -> handlers file

		  /meta/main.yml -> role dependencies

		  /tasks/main.yml -> tasks file can include smaller files if warranted

		  /templates/ -> file for use with the template resource

			   /npt.conf.j2 -> templates end in .j2

		  /vars/main.yml -> variables associated with this role

all.yml -> master playbook : master + nodes

master.yml -> playbook for master node tier

nodes.yml -> playbook for nodes tier

```
