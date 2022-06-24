# Arch Installation EFI + BIOS

---

## Network
```sh 
timedatectl set-ntp true
```

## Partioning
```sh 
lsblk -l  
cfdisk /dev/xxx 
```

#### Partition table
		
	    /dev/xxx1 250M                                                                                                              (X)
	    /dev/xxx2 16G  
	    Linux Swap    /dev/xxx4 ___G Linux File System

```sh 
lsblk -l
```

```sh 
mkfs.fat -f32 /dev/xxx1                                                                                                               (X)
mkswap /dev/xxx2
swapon /dev/xxx2
mkfs.ext4 /dev/xxx3
```

```sh 
lsblk -l
```

```sh 
mount /dev/xxx3 /mnt
mkdir /mnt/boot
mkdir /mnt/boot/efi                                                                                                                   (X)
mount /dev/xxx1 /mnt/boot/efi
```
## Installation
```sh 
pacstrap /mnt base base-devel linux linux-firmware vim reflector
genfstab -U /mnt - -  /mnt/etc/fstab 
```
!! To check (genfstab) 
```bash 
cat /mnt/etc/fstab
```
 
## System configuration
```sh 
arch-chroot /mnt
```

```sh
ln-sf /usr/share/zoneinfo/Asia/Kolkata /etc/localtime
 ``` 

```sh 
hwclock --systohc
```

```sh
vim /etc/locale.gen
```			
				uncomment en_US.UTF-8 UTF-8

```sh locale-gen
  echo Lang=en_US.UTF-8 -  /etc/locale.conf
  echo xdrd -  /etc/hostname
```

```sh vim etc/hosts
 	
 - 	 127.0.0.1  localhos
 - 	 ::1        localhost
 - 	 127.0.0.1  xdrd.localdomain xdrd
```
### Network Manager and grub Installation

```sh 
sudo pacman -S network manager grub bash-completion
```

```sh 
systemctl enable NetworkManager
```

```sh 
grub-install --target=x86_64-efi --efi- directory=/boot/efi                                                 (X)
```

BIOS-only
```sh 
grub-install --target=i386-pc /dev/xxx
```

	
```sh 
grub-mkconfig -o /boot/grub.cfg
```

```sh 
exit
umount -R /mnt
Reboot
   ```

## Post Installation

```sh 
useradd -m -g users -G wheel -S /bin/bash xdrd
passwd xdrd
EDITOR=vim vsudo
```
			uncomment % wheel All=(All)All

---

References: [Arch_Wiki_Installation](https://wiki.archlinux.org/title/Installation_guide) 

Related:[Arch_Wiki](https://wiki.archlinux.org/)
