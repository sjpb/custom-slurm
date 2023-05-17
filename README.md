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

To see the IP of the host (e.g. to ssh into it) run:

    terraform output

The built rpms will be in `~/rpmbuild/RPMS/x86_64/` on that host:

    [rocky@slurm-test ~]$ ls ~/rpmbuild/RPMS/x86_64/
    slurm-23.02.2-1.el8.x86_64.rpm                  slurm-pam_slurm-23.02.2-1.el8.x86_64.rpm
    slurm-contribs-23.02.2-1.el8.x86_64.rpm         slurm-perlapi-23.02.2-1.el8.x86_64.rpm
    slurm-devel-23.02.2-1.el8.x86_64.rpm            slurm-slurmctld-23.02.2-1.el8.x86_64.rpm
    slurm-example-configs-23.02.2-1.el8.x86_64.rpm  slurm-slurmd-23.02.2-1.el8.x86_64.rpm
    slurm-libpmi-23.02.2-1.el8.x86_64.rpm           slurm-slurmdbd-23.02.2-1.el8.x86_64.rpm
    slurm-openlava-23.02.2-1.el8.x86_64.rpm         slurm-torque-23.02.2-1.el8.x86_64.rpm
