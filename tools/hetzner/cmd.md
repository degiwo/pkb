## Setup

### Create non-root user

```bash
adduser user
usermod -aG sudo user
```

### Add ssh key for new user

```bash
mkdir -p /home/user/.ssh
sudo cp /root/.ssh/authorized_keys /home/user/.ssh/
sudo chown -R user:user /home/user/.ssh
sudo chmod 700 /home/user/.ssh
sudo chmod 600 /home/user/.ssh/authorized_keys
```

### Deactivate root and password login

```bash
sudo vim /etc/ssh/sshd_config
# set: PermitRootLogin no
# set: PasswordAuthentication no
# set: PubkeyAuthentication yes
sudo systemctl restart ssh
```

### Install Fail2Ban

```bash
sudo apt install fail2ban
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
```

### Install Docker & Docker Compose
