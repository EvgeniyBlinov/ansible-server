# ansible-server
ansible-server

## Usage

```
bin/run playbooks/vps.yml --skip-tags firewall

## test ssh and

bin/run playbooks/vps.yml --tags firewall
```

### @TODO

- backup

```
pam golang:
  - write to sqlite
  - run alert:
    golang read sqlite and send to chat
vpn:
  dependencies:
    - firewall
ingress:
  dependencies:
    - docker
    - docker-compose
```

- swapfile

```
fallocate -l 200M /swapfile || dd if=/dev/zero of=/dev/swapfile bs=1024 count=204800
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile

sysctl vm.swappiness=10
echo 'vm.swappiness=10' >> /etc/sysctl.conf
```
