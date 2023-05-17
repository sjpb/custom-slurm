# custom-slurm

Build an OpenHPC-compatible Slurm rpm

## Requirements

RockyLinux8.6 host

## Role Variables

See `vars/main.tf`.

## Dependencies

None.

## Example

The `example/` directory contains a `terraform` configuration to deploy a host and an `example.yml` playbook which runs
the role on that host.

### Setup

    cd example/
    python3.9 -m venv venv
    . venv/bin/activate
    pip install -U pip
    pip install ansible python-openstackclient

### Usage

    cd example/
    terraform init
    terraform apply
    ansible-playbook main.yml
