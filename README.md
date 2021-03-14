# ssh-keygen

Ed25519: high-speed high-security signatures
```bash
ssh-keygen -t ed25519 -C "shubhamtatvamasi@gmail.com"
```
```bash
cat ~/.ssh/id_ed25519.pub
```

Add your public key to the following file on a server 
```bash
vim ~/.ssh/authorized_keys
```
```bash
cat >> ~/.ssh/authorized_keys <<EOF
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP7Dd03PbcMXQTj+yDl/12a2XPfRFFV1YLEO8n8F5r69 shubhamtatvamasi@gmail.com
EOF
```
---

### AWS

Generate a key for AWS instances:
```bash
mkdir -p ~/.ssh/aws/
ssh-keygen -N '' -f ~/.ssh/aws/id_rsa
```

ssh to instance using it's public IP:
```bash
ssh -i ~/.ssh/aws/id_rsa ec2-user@8.8.8.8
```
---

Setup GCP
```bash
ssh-keygen -t ed25519 -C "shubham.tatvamasi@bitgrit.net" -f ~/.ssh/google_compute_engine
```
