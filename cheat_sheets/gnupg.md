# Encryption using GNU PG
---

### Generating a gpg key

```bash
gpg --full-gen-key
```


### Encrypting a file with that key

```bash
gpg -r user@email.com -e file
```


### Decrypting

```bash
gpg -d file.gpg 
```

---

References: [Luke's video on GPG](https://www.youtube.com/watch?v=DMGIlj7u7Eo), [Arch_wiki-GPG](https://wiki.archlinux.org/title/GnuPG)