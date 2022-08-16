Build a Kubernetes cluster local registry ubuntu


Second, edit `inventory/hosts` to match the system information.

For example:

```ini

[master]
192.168.154.20
192.168.154.21
192.168.154.22
[worker]
192.168.154.30
192.168.154.31
192.168.154.32
192.168.154.33
192.168.154.34
[nfs]
192.168.154.20
```

you must also edit `inventory/group_vars/all.yml` to match your environment.

For example:
```ini

server_hostname: master1
country_name: EG
city_name: cairo
organization_name: emu
email_address: salah@emu-eg.org
network_sub: 192.168.154.0/24
permission: u+rwx,g+rwx,o+rwx
myopts: 'rw,sync,hard'
owner: nobody
group: nogroup
```

## To run file 

Start provisioning of the cluster using the following command:

```bash
ansible-playbook site.yml -i inventory/hosts
```
