# oqs-openssh

Generate dilithium5 SSH key:
```bash
./ssh-keygen -t ssh-dilithium5
```

Check the public key:
```bash
cat ~/.ssh/id_dilithium5.pub
```

Change Port number to `2222`:
```bash
vim sshd_config
```

Start sshd server:
```bash
/home/ubuntu/openssh/sshd \
  -f ./sshd_config \
  -o KexAlgorithms=kyber-1024-sha512 \
  -o HostKeyAlgorithms=ssh-dilithium5 \
  -o PubkeyAcceptedKeyTypes=ssh-dilithium5 \
  -h ~/.ssh/id_dilithium5
```

Check if sshd server has started or not:
```bash
ps aux | grep sshd
```

Check if port `2222` is open:
```bash
telnet 172.30.1.166 2222
```

SSH into the system:
```bash
./ssh \
  -F ./ssh_config \
  -o KexAlgorithms=kyber-1024-sha512 \
  -o HostKeyAlgorithms=ssh-dilithium5 \
  -o PubkeyAcceptedKeyTypes=ssh-dilithium5 \
  -o PasswordAuthentication=no \
  -i ~/.ssh/id_dilithium5 \
  -p 2222 \
  ubuntu@172.30.1.166
```
