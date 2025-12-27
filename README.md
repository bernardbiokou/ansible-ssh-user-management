## Ansible SSH User Management

This repository demonstrates a simple and reproducible approach to managing Linux users and SSH public keys across multiple servers using Ansible.

The goal is to replace manual SSH key management with a Git-driven, auditable, and automated workflow.

## Why this project exists
SSH access is often managed manually:

- keys copied from server to server
- no clear view of who has access
- former users sometimes left behind
- no audit trail

## This repository shows a clean alternative:

- one source of truth
- consistent enforcement
- predictable onboarding and off-boarding

## What this repository shows
This project demonstrates:

- centralized SSH user management
- declarative user state (present / absent)
- automated key installation
- clean user removal (including home directories)
- Git-based auditability

It focuses on the technical approach, not on organizational policies.

## Project structure
ssh-access/
├── group_vars/
│   └── all.yml
├── inventory/
│   └── hosts.yml
├── manage_users.yml
└── roles/
    └── users/
        └── tasks/
            └── main.yml

## What each part represents
inventory/hosts.yml
Defines the hosts managed by Ansible.

group_vars/all.yml
Declares users, their desired state, and their SSH keys.

roles/users/tasks/main.yml
Applies the logic:
- create users
- remove users and home directories
- manage authorized_keys

manage_users.yml
Playbook orchestrating the role across all hosts.

This structure can be adapted to environments of different sizes.

### High-level usage
You will need:

- Ansible installed
- SSH connectivity to your servers
- An inventory matching your infrastructure

### Typical workflow:
- Declare users in group_vars/all.yml
- Define hosts in inventory/hosts.yml
- Run the playbook to enforce the desired state

### How you integrate this into CI, workflows, and security processes depends on your environment.
This repository shows the approach, not a full production playbook.

Important considerations:
- state: absent removes the user and their home directory
- Always test in non-production environments first
- Avoid manual user or key changes once automation is in place
- Treat Git history as your audit trail
- Going further: production-ready guidance
- This repository intentionally stays minimal.

If you want a step-by-step, production-ready implementation, including:

- full walkthrough
- operational and security conventions
- onboarding and off-boarding standards
- Git audit conventions
- safety checklists
- real-world usage guidance

A complete Starter Pack is available here:

https://aloba.gumroad.com/l/ssh-user-management-ansible

### Final note
This repository is meant to be a reference implementation.
Adapt it to your organization’s security policies and operational requirements.
