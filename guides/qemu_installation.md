# QEMU installation

### Required Pacakages
``` bash
sudo pacman -S qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat libguestfs ebtables iptables 
```
- Otional for UEFI support
```bash
sudo pacman -S edk2-ovmf
​
```

### Start the Service
```bash
sudo systemctl enable libvirtd.service
sudo systemctl start libvirtd.service
```

### Enable user account for KVM
```bash
sudo vim /etc/libvirt/libvirtd.conf
```

### Editing libvirtd.conf
 ***uncomment the following line in /etc/libvirt/libvirtd.conf***
- unix_sock_group = "libvirt"
- unix_socket_ro_perms = "0770"
- unix_sock_rw_perms = "0770"

### Add user account to libvirt group
``` bash
sudo usermod -aG libvirt $(whoami)
newgrp libvirt
sudo systemctl restart libvirt.service
```
## DONE 

### Additional Stuff

##### Adding a shared folder form host to VM

```bash
sudo mount -t 9p -o trans=virtio /$mountpoint $folder
```

or to auto mount in fstab
```bash
/$mountpoint /home/usr/$folder 9p trans=virtio,version=9p2000.L,rw 0 0
```


##### To fix network error

```
sudo virsh net-start default 
```
