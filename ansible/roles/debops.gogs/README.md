# Lenticular Debops

## DISCLAMER

This project is still under havy development and have a lot of bugs.
Please make a github issue or a pullrequest if you find something.

## Intro

This is the reference ansible implementation of the [Lenticular Ldap Admin management tool](https://github.com/LenticularCloud/Cloud-Ldap-Admin).
The goal is to have a ansible script that can setup a cloud system by changing a few parameters.

It should be easy for everyone to host his/her/* own data on a open source system that is under his/her/* control.

## Services

 * auth (ldap) (docs needed)
 * mail (dovecot/postfix) (planned)
 * git (git gogs)  (docs needed)
 * jabber (prosody) (docs needed)
 * calendar/contacts (radicale) (docs needed)
 * filesync/share (seafile) (planned)
 * vpn (openvpn) (plannned)
 * shell (openssh) (delayed spectre/meltdown)

## Requirements

Clean debian installation with a public ipv4 and public ipv6 `/64` network.
DNS access to a domain or subdomain, lots of subdomains are needed.

RAM: @TODO
Storage: @TODO

## Settings

Main settings are found here:

 * ansible/inventory/host_vars/milliways.info.yml
 * ansible/inventory/hosts
 * ansible/inventory/*

## run

### git-crypt

`apt install git-crypt`
`man git-crypt`

### DNS

@TODO list with needed subdomains

### debops

```bash

#bootstrap main machine
debops bootstrap -l cloud_main

#setup main machine
debops -l cloud_main

#start lxc containers
debops ansible/playbooks/lxc.yml

# bootstrap lxc containers
debops bootstrap --limit lxc

# setup all services
debops

# extra playbooks
debops ansible/playbooks/prometheus.yml
```

## Contributers/Thanks

Currently Contributers to this repository:

 * TuxCoder <git (æt) o-g.at>

Thanks to everyone from the DebOps Project!

