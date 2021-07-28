# mk's ansible

This is my ansible setup for setting up the kubernetes cluster in my home lab.

## Requirements

* [Vagrant]
* [Ansible]
* [Debian] on the nodes (Buster (aka version 10) or newer)

## Creating a VM cluster

For this you'll also need [Vagrant], a machine with at least 12 GiB of RAM and
it's best if you have a cpu with more than 12 threads - but it should also work
with less.

The `Vagrantfile` is set up to create 3 control plane nodes and 3 data plane
nodes.

The VM's are configured to use the IP subnet `192.168.50.0/23` for the control
plane nodes, and `192.168.51.0/23` for the data plane nodes.

### Ansible dependencies

The ansible tasks use some collections that are available on [Ansible Galaxy].

To install them, run

`ansible-galaxy install -r requirements.yaml`

### Starting the VMs

To start the virtual machines, run

`vagrant up`

Once the machines are up, you can go ahead and run the ansible playbook.

## Running the ansible playbook

To run the ansible playbook, simply run

`ansible-playbook site.yml`

[ansible]: https://ansible.com/
[ansible galaxy]: https://galaxy.ansible.com/
[debian]: https://www.debian.org
[vagrant]: https://www.vagrantup.com/
