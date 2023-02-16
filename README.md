# ansible_controller

## Reconcile Ansible Controller GitOps Style

Four key principles of GitOps (a term coined by WeaveWorks)

1. Describe the desired state of the whole system using a declarative specification.
1. There is a convergence mechanism to bring the desired and observed states in sync.
1. Hence all Git commits cause verifiable and idempotent updates in the cluster.
1. Convergence is eventual.

## Bootstrapping the Controller

When we want to adhere to these principles we need to bootstrap the configuration so that:

- An organization with galaxy_credentials is present
- Minimal credentials types: Source Control, Vault, Machine
- A controller project like this repo
- An inventory with localhost
- A job template from the controller project to run the playbook with the credentials.

## GitOps Controller Configuration

- This repo has [controller configuration](https://github.com/playingfield/ansible_controller/tree/main/inventory/group_vars/controller)
- Controller configuration manages the Ansible Controller, and adds [ansible_project.git](https://github.com/playingfield/ansible_project) and [ansible_inventory](https://github.com/playingfield/ansible_inventory) as demo.
- Forks of this repo can be used to define your whole infra GitOps style.
- No need to use the API
- No need to write setup playbooks.
