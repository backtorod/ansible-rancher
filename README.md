# Rancher Labs Provisioning with Ansible

Despite the fact that Rancher Labs can easily be installed ( a couple of Docker containers to spin up), we decided to make it even easier and somehow make it a kind of framework for future work or integrations.

This project is initially intended to work locally, however can be adapted for a more complex provisioning.

## Requirements

1. Ansible
2. Docker

## Installation

1. Clone this repository
```bash
git@github.com:rguareschi/ansible-rancher.git
```

## Usage

1. To provision the complete stack, run the **provision_master.yml** playbook:
```bash
pushd ansible-rancher
ansible-playbook -vvv \
  --ask-sudo-pass \
  --user ${USER} \
  provision_rancher.yml
```

2. Role **rancher_master** will add the following entry on /etc/hosts:
   To modify default values (IP address, FQDN and comment), check the **vars/global.yml** file for *rancher_server, rancher_fqdn and rancher_hosts_comment* variables
```bash
192.168.2.180 rancher.local # Added by Ansible Rancher Labs Provisioning
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

* Feature: integrate ansible-vault
* Feature: external provisioning (not only local)
* Feature: adding external hosts

## Feedback

All bugs, feature requests, feedback, etc., are more than welcome.

## License

BSD

## Author Information

**Original**
github.com/galal-hussein/Rancher-Ansible

**Modified by**
github.com/rguareschi
