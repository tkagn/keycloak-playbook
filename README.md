# keycloak-playbook

Playbooks to deploy a single sign-on (SSO) server on host(s). The host(s) are defined in the inventory.

# Table of Contents

- [Prerequisites](#Prerequisites)
- [Files](#Files)
- [Usage](#Usage)
- [References](#References)

## Keycloak

Keycloak is an Open Source Identity and Access Management solution for modern Applications and Services. Keycloak is the upstream project for Red Hat Single Sign-On (RH-SSO).


## Prerequisites

- RHEL or Fedora system
- Ansible 2.9 or greater

## Files

- keycloak-day1.yaml - Install keycloak server
- keycloak-day1day2.yaml - Install keycloak server, define realm, configure roles and users, and define clients
- inventory - Ansible inventory file
- ansible.cfg - ansible configuration file

## Usage

Install the collecton

```bash
ansible-galaxy collection install middleware_automation.keycloak
ansible-galaxy collection list
```

Run the playbook(s):

```bash
ansible-playbook -i inventory keycloak-day1.yaml
```

or 

```bash
ansible-playbook -i inventory keycloak-day1day2.yaml
```


Deploy Keycloak Quarkus version:

```bash
ansible-playbook -i invnetory keycloak_quarkus.yaml
```

Deploy Red Hat SSO:

```bash
ansible-playbook -i inventory rhsso.yaml
```

Validate by accessing http://keycloak-host:8080

## References

- Keycloak - https://www.keycloak.org/
- Keycloak GitHub - https://github.com/keycloak/keycloak
- Red Hat Single Sign-On - https://access.redhat.com/products/red-hat-single-sign-on
- Deploy Keycloak single sign-on with Ansible - https://developers.redhat.com/articles/2022/04/20/deploy-keycloak-single-sign-ansible#
- Automate your SSO with Ansible and Keycloak - https://developers.redhat.com/articles/2023/02/20/automate-your-sso-ansible-and-keycloak?sc_cid=7013a0000034pQnAAI#install_keycloak_with_ansible 
- Ansible Collection - middleware_automation.keycloak GitHub - https://github.com/ansible-middleware/keycloak