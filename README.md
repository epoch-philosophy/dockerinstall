# dockerinstall
Boring template for Ubuntu Server. I usually find new reasons to spin up a server and want a simple way to automate common installations without Ansible. Copy and paste is easier sometimes!

```bash
# Update Apt so I can use HTTPS:
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

```bash
# Add Docker’s GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```bash
# Make repository stable:
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
# Update and installation
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose
```

```bash
# Make sure it works
sudo docker run hello-world
