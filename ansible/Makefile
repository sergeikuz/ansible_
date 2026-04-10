.PHONY: help update-cache install-packages create-users all

help:
	@echo "Available commands:"
	@echo "  make update-cache    - Update package manager cache"
	@echo "  make install-packages - Install Git, Make, Node.js"
	@echo "  make create-users    - Create users: arya, sansa, tirion"
	@echo "  make all             - Run all tasks"
	@echo "  make ping            - Run all ping"

update-cache:
	ansible-playbook setup-server.yml -i inventory.ini -t update-cache

install-packages:
	ansible-playbook setup-server.yml -i inventory.ini -t install-packages

create-users:
	ansible-playbook setup-server.yml -i inventory.ini -t create-users

all:
	ansible-playbook setup-server.yml -i inventory.ini

ping:
	ansible all -i inventory.yml -u sergei -m ping
