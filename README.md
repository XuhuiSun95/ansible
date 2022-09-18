# ansible

### Prerequisite
- Ansible
- Oh my zsh ansible plugin

### Proxmox VM
#### VM configuration automations
```bash
aplaybook -i staging proxmox-vm/site.yml --user <vm user>
```
#### VM extend file system after resizing a volume
similar to the [AWS EC2 example](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html).

subject to on your file system:
```bash
sudo growpart /dev/sda 1
sudo resize2fs /dev/sda1
```
