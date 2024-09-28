Hi, ![](https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif)my name is Serhii Shypylov
=========================================================================================================================================

💛 I am a Linux System administrator engineer with DevOps practices. I have several certificates in Linux, Docker, Ansible and Terraform and continue to learn more. I like everything related to Docker, containers and IT technologies in general. I love solving complex IT solutions.
-------------------------------

* 💼 Looking for a job
* 🌍 I'm based in Poznan
* 🖥️ See my [LinkedIn](https://github.com/Shipssv83) profile 
* 👾 Chat with IT pros on [Discord](https://discord.com/shipssv_19055)\
* 📧 Reach me at ships@ukr.net
* 🧠 I'm learning DevOps Practices

### Socials

<p align="left"> <a href="https://github.com/Shipssv83" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" width="32" height="32" /> </picture> </a> <a href="https://www.linkedin.com/in/sergey-shipilov-7262a31b4/" target="_blank" rel="noreferrer"> <picture> <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin-dark.svg" /> <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" /> <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/linkedin.svg" width="32" height="32" /> </picture> </a></p>

# Ansible Playbook for Server, Docker, and Pritunl VPN Installation

This project contains Ansible playbooks for setting up a server, installing Docker, and deploying Pritunl VPN in a Docker container.

## Overview

The project includes the following steps:
1. **Server Setup**: Configuring basic server settings, such as the timezone.
2. **Docker Installation**: Installs Docker and Docker Compose on the target server.
3. **Pritunl VPN Installation**: Deploys the Pritunl VPN server inside a Docker container.

## Playbook Structure

### 1. Server Setup (`server-install.yml`)
This playbook installs the necessary packages and performs basic system setup.

### 2. Docker Installation (`docker-install.yml`)
The `docker-install.yml` playbook installs Docker and Docker Compose, preparing the server for containerization.

### 3. Pritunl VPN Installation (`pritunl-docker-install.yml`)
This playbook installs the Pritunl VPN server inside a Docker container, setting up VPN ports and configuring UFW rules to allow access.

## Variables

Here are the configurable variables for this project:

- `timezone`: The server's timezone (default: `Europe/Warsaw`).
- `pritunl_docker_version`: The version of Pritunl VPN to be installed (default: `latest`).
- `pritunl_vpn_port`: The port used by Pritunl VPN for connections (default: `14830`).
- `wg_vpn_port`: The port for WireGuard VPN (default: `51820`).
- `pritunl_web`: The port for accessing the Pritunl web interface (default: `443`).

### Example Configuration:

```yaml
vars:
  timezone: 'Europe/Warsaw'
  pritunl_docker_version: 'latest'
  pritunl_vpn_port: '14830'
  wg_vpn_port: '51820'
  pritunl_web: '443'
```

# ansible galaxy roles
```
### install role ansible galaxy
ansible-galaxy install -r roles/requirements.yml

### upgrade role ansible galaxy 
ansible-galaxy install -g -f -r roles/requirements.yml
```

# Run the Playbook install
Run the playbook by specifying your inventory file and variable file:

```
ansible-playbook -i inventory --user root --extra-vars "host=host_name" playbooks/pritunl-docker-install.yml
```

License
This project is licensed under the MIT License