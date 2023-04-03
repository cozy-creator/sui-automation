# sui-automation
Deploy Sui Fullnodes with Ansible

## Prerequisites
- Install Ubuntu 20.04 LTS on your server.
- Create user 'sui' with root privileges and no password auth required.
`sudo adduser sui`
`sudo visudo`
In visudo, add the following line:
`sui     ALL=(ALL:ALL) NOPASSWD: ALL`
- Generate ssh key on the machine where you will run Ansible.
`ssh-keygen`
- Copy ssh key to the full node server, for user sui.
ssh-copy-id -i /path/to/your/key sui@your-fullnode-ip

## Example ini Config
[fullnodes]
ip-address-1
ip-address-2

[fullnodes:vars]
ansible_user = sui
ansible_private_key_file = /absolute/path/to/local/ssh/key
sui_branch = testnet
