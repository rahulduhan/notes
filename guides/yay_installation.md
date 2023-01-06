# yay insallation

1. First install git if not installed already
```bash
sudo pacman -S git --noconfirm
```

2. Clone the yay repo
```bash
git clone https://aur.archlinux.org/yay.git
```

3. Cd into yay and build yay
```bash
cd yay
makepkg -si
```

4. Done. yay ready for use
	remove yay directory for cleanup 
```bash
cd .. && rm -rf yay
```