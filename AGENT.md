# AGENT.md — Instructions for AI Agents

## Project Overview

Ansible learning project for automating server configuration and deployment.

## Repository Structure

```
ansible/
├── ansible.cfg              # Ansible configuration (host_key_checking = False)
├── inventory.ini            # Server inventory (webservers, appservers groups)
├── requirements.yml         # Ansible Galaxy dependencies
├── foo_role/                # Study role
├── foo_second_role/         # Study role
└── roles/
    └── user_setup/          # Developer environment setup role
```

## Commands

### Install Galaxy dependencies
```bash
ansible-galaxy install -r ansible/requirements.yml
```

### Run playbooks
```bash
ansible-playbook -i ansible/inventory.ini ansible/roles/setup_dev_env.yml
```

### Run with verbose output
```bash
ansible-playbook -i ansible/inventory.ini <playbook.yml> -vvv
```

### Lint (if ansible-lint installed)
```bash
ansible-lint ansible/
```

## Conventions

- All Ansible files live under `ansible/`
- Roles follow standard Ansible role structure (tasks, handlers, templates, vars, defaults, meta, files, tests)
- Templates use `.j2` extension
- Inventory uses INI format with group variables
- `host_key_checking = False` in ansible.cfg (dev environment only)

## Git Workflow

- Branch: `main`
- Commit messages: conventional style (feat, fix, docs, etc.)
- Push directly to `main` (personal learning project)
