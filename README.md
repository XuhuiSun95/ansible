# ansible

### Prerequisite
- Ansible
- Oh my zsh ansible plugin

### Proxmox VM
#### VM configuration automations
subject to your cloud-init user:
```bash
aplaybook -i inventory/staging proxmox-vm/site.yml --user sys-admin
```

#### VM extend file system after resizing a volume
similar to the [AWS EC2 example](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html).

subject to your file system:
```bash
sudo growpart /dev/sda 1
sudo resize2fs /dev/sda1
```

### K3s
#### Ansible Galaxy requirements
```bash
agal install -r k3s-ansible/collections/requirements.yml
```

### K3s configuration automations
update `inventory/staging/group_vars/k3s_cluster.yml` for your config:
```bash
aplaybook -i inventory/staging k3s-ansible/site.yml
```
