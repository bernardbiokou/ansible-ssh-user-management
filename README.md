# Ansible SSH User Management

Manage Linux SSH users and public keys **as code**, from a **single source of truth**.

This project helps you **standardize onboarding and offboarding** across multiple servers using Ansible - without relying on manual SSH access or ad-hoc scripts.

The repository provides the **core automation logic**.  
Production guidance, real-world usage patterns, and operational checklists are available in the **Production Pack** (paid).

---

## Why this project exists

In many infrastructures:
- SSH users are added manually
- Keys stay forever
- Access reviews are painful
- Offboarding is risky and inconsistent

This leads to:
- security drift
- unclear ownership
- no audit trail

This project enforces **predictable, auditable SSH access management** using a simple YAML-based workflow.

---

## What you get here (Free)

This repository includes:

- ✔️ Centralized SSH user & key management
- ✔️ Declarative YAML configuration
- ✔️ Onboarding and offboarding via `present / absent`
- ✔️ Reproducible execution across servers
- ✔️ Git-friendly (diffs, reviews, history)

This is a **minimal but solid foundation** you can test or extend.

> ⚠️ This repo focuses on *automation logic*, not production operations or governance.

---

## Typical use cases

- Solo sysadmin managing multiple servers
- Small IT teams without DevOps
- SMEs needing controlled SSH access
- Consultants standardizing client environments

---

## Quick start

```bash
git clone https://github.com/bernardbiokou/ansible-ssh-user-management.git
cd ansible-ssh-user-management
ansible-playbook -i inventory/hosts.yml manage_users.yml
```


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
  group_vars/
    all.yml        # Users and SSH keys (single source of truth)
  inventory/
    hosts.yml      # Target hosts
  manage_users.yml # Main playbook
  roles/
    users/
      tasks/
        main.yml

This structure is intentionally simple and easy to audit.

## Production Pack (Paid)
If you want to run this safely in production, the Production Pack provides everything that is not included here:

✅ Step-by-step production deployment guide
✅ Real-world usage patterns (SME, contractors, multiple environments)
✅ Access review & offboarding checklists
✅ Git workflow conventions for SSH access
✅ Rollback & validation strategies
✅ Common pitfalls and troubleshooting

👉 Get the Production Pack here:
https://aloba.gumroad.com/l/ssh-user-management-ansible

You keep the code. You pay for clarity, safety, and time saved.

## FAQ
Is this production-ready out of the box?
The automation works, but production requires processes, reviews, and discipline.
That operational layer is covered in the Production Pack.

Why isn’t everything documented here?
This repository stays minimal and accessible.
Detailed production guidance and real-world scenarios are packaged separately.

Can I adapt this to my infrastructure?
Yes. The design is intentionally simple and extensible.

## License
MIT License - commercial use is allowed.
