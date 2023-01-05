# Automount drives

1. Make a directory where you want to automount. Eg: 
```bash 
mkdir /mnt/data
```


2. Use blkid to know the uuid of the drive
```bash
sudo blkid
```

3. Add the entery of the drive with the UUID with the fstab
```bash
sudo vim /etc/fstab
```

4. Reboot 