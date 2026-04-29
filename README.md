<!-- This was created with Claude Code -->

# App Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-App)


This directory contains Ansible automation for app management and operations.

## Overview

The App automation provides playbooks and roles for managing and configuring
app infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [eap_app_validate](roles/eap_app_validate/README.md) | Role for eap app validate |
| [eap_vm_combine](roles/eap_vm_combine/README.md) | Role for eap vm combine |
| [install_eap](roles/install_eap/README.md) | Role for install eap |
| [install_eap_app](roles/install_eap_app/README.md) | Role for install eap app |
| [jcbs_prep](roles/jcbs_prep/README.md) | Role for jcbs prep |
| [postgresql](roles/postgresql/README.md) | Role for postgresql |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| eapappinstall.yml | Playbook for eapappinstall | {{ vm_name }} |
| eapinstall.yml | Playbook for eapinstall | {{ vm_name }} |
| threetierapp.yml | Playbook for threetierapp | localhost, pgsql, jbcs |
| threetiervmcombine.yml | Playbook for threetiervmcombine | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run eapappinstall.yml

# Run in stdout mode
ansible-navigator run eapappinstall.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - eap_app_validate
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-App/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
