# Arch Installation EFI + BIOS

---

## Network
>timedatectl set-ntp true

## Partioning
>lsblk -l
  cfdisk /dev/sdx 

#### Partition table
		
	    /dev/sdx1 250M                                                           (X)
	    /dev/sdx2 16G  
	    Linux Swap    /dev/sdx4 ___G Linux File System

>lsblk -l

>mkfs.fat -f32 /dev/sdx1                                                                                                          (X)
  mkswap /dev/sdx2
  swapon /dev/sdx2
  mkfs.ext4 /dev/sdx3

>lsblk -l

>mount /dev/sdx3 /mnt
  mkdir /mnt/boot
  mkdir /mnt/boot/efi                                                                                                                 (X)
  mount /dev/sdx1 /mnt/boot/efi

## Installation
>pacstrap /mnt base base-devel linux linux-firmware vim reflector
  genfstab -U /mnt >> /mnt/etc/fstab 

!! To check (genfstab) 
 >cat /mnt/etc/fstab
 
## System configuration
>arch-chroot /mnt

>ln-sf /usr/share/zoneinfo/Asia/Kolkata /etc/localtime
  
>hwclock --systohc

>vim /etc/locale.gen
				
				uncomment en_US.UTF-8 UTF-8
>locale-gen
  echo Lang=en_US.UTF-8 > /etc/locale.conf
  echo xdrd > /etc/hostname

>vim etc/hosts
>	
>>	127.0.0.1  localhos
>>	 ::1        localhost
>>	 127.0.0.1  xdrd.localdomain xdrd

### Network Manager and grub Installation

>sudo pacman -S network manager grub bash-completion
   
>systemctl enable NetworkManager

>grub-install --target=x86_64-efi --efi- directory=/boot/efi                                                 (X)

BIOS-only
>grub-install --target=i386-pc /dev/sdx

	
>grub-mkconfig -o /boot/grub.cfg

>exit
>umount -R /mnt
>Reboot

## Post Installation

>useradd -m -g users -G wheel -S /bin/bash xdrd
>passwd xdrd
>EDITOR=vim vsudo

			uncomment % wheel All=(All)All

# End

References: [Arch_Wiki_Installation](https://wiki.archlinux.org/title/Installation_guide) 

Related:[Arch_Wiki](https://wiki.archlinux.org/)