# Huracan Indexer Automation
Ansible playbooks to deploy everything you need to operate the Huracan Indexer.

## Components
- Custom Rust indexing application.
- Sui Fullnode
- MongoDB Cluster
- Externally managed logging and metric services.

## Prerequisites

- Install Ubuntu 20.04 LTS on your server.
- Create user 'sui' with a password of your choice.
`sudo adduser sui`
`sudo visudo`
In visudo, add the following line to allow root operations without a password:
`sui     ALL=(ALL:ALL) NOPASSWD: ALL`
- Generate ssh key on the machine where you will run Ansible.
`ssh-keygen`
- Copy ssh key to the full node server, for user sui. It will ask for the password you set ealier.
`ssh-copy-id -i /path/to/your/public-key sui@your-fullnode-ip`

## Example ini Config
[fullnode]
ip-address-1
ip-address-2

[fullnode:vars]
ansible_user = sui
ansible_private_key_file = /absolute/path/to/local/ssh/key
sui_branch = testnet
# Generate this token in Betterstack UI:
logtail_source_token = xxxxx

