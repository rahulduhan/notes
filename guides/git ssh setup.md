# git ssh setup

1. Generate new SSH key and optionally add a passphrase

```bash 
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. Start ssh-agent in background

```bash
eval "$(ssh-agent -s)"
```

3. Add SSH private key to the ssh-agent

```shell
ssh-add ~/.ssh/id_ed25519
```

	replace _id_ed25519_ in the command with the name of your private key file.

4. Get the public key for setup

```bash
cat .ssh/id_ed25519.pub | xclip -selection c
```